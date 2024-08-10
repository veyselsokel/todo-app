<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-100">
        <div class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
            <h1 class="text-3xl font-bold text-center mb-6 text-gray-800">Todo Listesi</h1>
            <TodoList :todos="todos" @delete-todo="deleteTodo" @update-todo="updateTodo" />
            <TodoForm @add-todo="addTodo" />
        </div>
    </div>
</template>

<script>
import TodoList from './components/TodoList.vue';
import TodoForm from './components/TodoForm.vue';
import axios from 'axios';

export default {
    components: { TodoList, TodoForm },
    data() {
        return {
            todos: []
        };
    },
    methods: {
        async fetchTodos() {
            try {
                const response = await axios.get('/todos');
                this.todos = response.data;
            } catch (error) {
                console.error('Error fetching todos:', error);
            }
        },
        async addTodo(newTodo) {
            try {
                const response = await axios.post('/todos', newTodo);
                this.todos.push(response.data);
            } catch (error) {
                console.error('Error adding todo:', error);
            }
        },
        async updateTodo(todo) {
            try {
                await axios.put(`/todos/${todo.id}`, { completed: todo.completed });
            } catch (error) {
                console.error('Error updating todo:', error);
            }
        },
        async deleteTodo(id) {
            try {
                await axios.delete(`/todos/${id}`);
                this.todos = this.todos.filter(todo => todo.id !== id);
            } catch (error) {
                console.error('Error deleting todo:', error);
            }
        }
    },
    mounted() {
        this.fetchTodos();
    }
}
</script>