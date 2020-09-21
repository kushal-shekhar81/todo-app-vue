<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p> 
            <input type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed">
            {{todo.title}} 
            <button class="btn btn-primary btn-sm del" v-on:click="$emit('del-todo',todo.id)"> X </button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: {
        todo: {
            type: Array
        }
    },
    methods: {
        markComplete() {
            // eslint-disable-next-line vue/no-mutating-props
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .todo-item {
        padding: 10px;
        padding-left: 30px;
        align-items: center;
        justify-content: center;
        border-bottom: 1px solid black;
    }
    
    .is-completed {
        text-decoration: line-through;
    }

    .del {
        
        margin-left: 70px;
    }

</style>