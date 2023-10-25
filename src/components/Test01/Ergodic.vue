<script setup>
    import { ref } from 'vue'
    import TodoListItem from './TodoListItem.vue'
    const todoText = ref('');
    const todoList = ref([
        {
            id: 1,
            title: 'vue1'
        },
        {
            id: 2,
            title: 'vue2'
        },
        {
            id: 3,
            title: 'vue3'
        }
    ]);
    let todoId = 4;
    function addTodoList() {
        todoList.value.push({
            id: todoId++,
            title: todoText.value
        })
        todoText.value = '';
    }
</script>
<template>
    <form>
        <label for="new-todo">add a todo</label>
        <input type="text" id="new-todo" v-model="todoText">
        <button type="button" @click="addTodoList">add</button>
    </form>
    <ul>
        <TodoListItem
               v-for="(todo, index) in todoList"
               :key="todo.id"
               :title="todo.title"
               @remove="todoList.splice(index, 1)"
        />
    </ul>
</template>
<style scoped>
</style>
