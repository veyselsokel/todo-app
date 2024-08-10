<template>
    <ul>
        <li v-for="todo in todos" :key="todo.id"
            class="flex items-center justify-between mb-4 p-2 bg-gray-50 rounded-lg">
            <div class="flex items-center">
                <input type="checkbox" v-model="todo.completed" @change="$emit('update-todo', todo)" class="mr-2">
                <span :class="{ 'line-through text-gray-400': todo.completed, 'text-gray-800': !todo.completed }">{{
            todo.title }}</span>
            </div>
            <button @click="$emit('delete-todo', todo.id)"
                class="bg-red-500 text-white rounded-full px-4 py-1 text-sm">Sil</button>
        </li>
    </ul>
</template>

<script>
export default {
    props: ['todos']
}
</script>