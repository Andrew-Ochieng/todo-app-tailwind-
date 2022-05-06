<template>
    <div>
        <form @submit="addTodo" method="post">
            <input v-model="title" name="title" class="border-none w-full bg-gray-100 p-2 my-4 rounded-md" type="text" placeholder="Add Todo..">
            <input class="w-full py-2 text-white hover:text-gray-900 bg-green-400 hover:bg-green-300 rounded-md hover:-translate-y-1 hover:scale-104 duration-500" type="submit" value="Submit">
        </form>
    </div>
</template>

<script>
// import uuid from 'uuid';

    export default {
        name: 'AddTodo',
        data() {
            return {
                title: ''
            }
        },
        methods: {
            addTodo (e) {
                e.preventDefault();

                const newTodo = {
                    id: '',
                    title: this.title,
                    completed: false

                }

                //send up to parent
                this.$emit('add-todo', newTodo);

                this.title = '';
            }
        },
    }
</script>

<style scoped>


</style>