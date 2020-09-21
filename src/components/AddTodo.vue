<template>
    <div class="container mb-5">
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" placeholder="Add todo" >
            <input type="submit" class="btn btn-primary ml-5" value="Submit">
        </form>
    </div>
</template>

<script>

import {v4 as uuidv4} from 'uuid';

export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }

            this.$emit('add-todo',newTodo)
            this.title = ''
        }
    }
}
</script>

