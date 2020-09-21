<template>
    <div v-for="todo in todos" v-bind:key="todo.id">
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
    </div>
</template>

<script>

import TodoItem from './TodosItem';
export default {
    name: "TodosList",
    components: {
        TodoItem
    },
    props: {
        todos: {
            type: Array
        }
    }
}
</script>