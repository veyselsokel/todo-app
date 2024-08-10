<template>
    <li>
        <input type="checkbox" v-model="todo.completed" @change="emitUpdate">
        <span :class="{ 'line-through': todo.completed }">{{ todo.title }}</span>
        <button @click="emitDelete">Sil</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true,
        }
    },
    methods: {
        emitUpdate() {
            this.$emit('update-todo', this.todo);
        },
        emitDelete() {
            this.$emit('delete-todo', this.todo.id);
        }
    }
}
</script>

<style scoped>
.line-through {
    text-decoration: line-through;
}
</style>
