<template>
    <div class="flex mt-6">
        <input v-model="newTodo.title" placeholder="Yeni Todo" @keyup.enter="submitTodo"
            class="flex-grow border border-gray-300 rounded-l-lg p-2 text-gray-800" />
        <button @click="submitTodo" class="bg-blue-500 text-white px-4 py-2 rounded-r-lg">Ekle</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodo: {
                title: '',
                completed: false
            }
        };
    },
    methods: {
        submitTodo() {
            this.$emit('add-todo', { ...this.newTodo });
            this.newTodo.title = '';
        }
    }
}
</script>