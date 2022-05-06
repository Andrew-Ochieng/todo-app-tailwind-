<template>
    <div>
        <h3 class="text-center font-semibold mt-8 mb-4">Todo List</h3>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
            <!-- <ul class="my-2 p-2 rounded-md bg-blue-200">{{todo.title}}</ul> -->
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem.vue"

    export default {
        name: 'Todos',
        components: {
            TodoItem
        },
        props: ["todos"]
    }
</script>

<style lang="scss" scoped>

</style>