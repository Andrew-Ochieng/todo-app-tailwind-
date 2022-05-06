<template>
    <div>
        <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
            <ul class="my-4 p-2 rounded-md bg-blue-200">
                <input v-on:change="markComplete" type="checkbox" class="w-6 rounded-full shadow">
                {{todo.title}}
                <button @click="$emit('del-todo', todo.id)" class="float-right bg-red-400 px-2 rounded-full mx-2 text-white">x</button>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'TodoItem',
        props: ["todo"],
        methods: {
            markComplete() {
                this.todo.completed = !this.todo.completed
            }
        },
    }
</script>

<style scoped>
.is-complete {
    text-decoration: line-through;
    color: red;
}

.del{
    border:none;
    cursor: pointer;
}



</style>