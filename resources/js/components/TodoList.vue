<template>
    <ul>
        <li v-for="todo in todos" :key="todo.id"
            class="flex items-center justify-between mb-4 p-2 bg-gray-50 rounded-lg">
            <div v-if="!todo.isEditing" class="flex items-center">
                <input type="checkbox" v-model="todo.completed" @change="$emit('update-todo', todo)" class="mr-2">
                <span class="w-16"
                    :class="{ 'line-through text-gray-400': todo.completed, 'text-gray-800': !todo.completed }">
                    {{ todo.title }}
                </span>
            </div>
            <div class="flex flex-col gap-2" v-else>
                <input type="text" v-model="todo.title" class="border p-1 rounded-md">
                <button @click="$emit('save-edit', todo)"
                    class="bg-green-500 text-white rounded-full px-4 py-1 text-sm">Kaydet</button>
                <button @click="todo.isEditing = false"
                    class="bg-gray-500 text-white rounded-full px-4 py-1 text-sm">İptal</button>
            </div>
            <button v-if="!todo.isEditing" @click="todo.isEditing = true"
                class="bg-blue-500 rounded-full px-4 py-1 text-white text-sm">Düzenle</button>
            <button @click="$emit('delete-todo', todo.id)"
                class="bg-red-500 text-white rounded-full px-4 py-1 text-sm">Sil</button>
            <div class="text-xs max-w-max">{{ formatDate(todo.created_at) }}</div>
        </li>
    </ul>
</template>

<script>
import moment from 'moment';

export default {
    props: ['todos'],
    methods: {
        formatDate(date) {
            return moment(date).format('MM Do YYYY, h:mm');
        }
    }
}
</script>

<style scoped>
.line-through {
    text-decoration: line-through;
}
</style>
