<template>
  <div class="md:mx-72 mx-8 my-8">
    <div class="bg-blue-400 rounded-t-3xl rounded-b-3xl p-8">
      <TodoHeader />
      <AddTodo v-on:add-todo="addTodo"/>
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
      <TodoFooter />
    </div>
    
  </div>
</template>

<script>
import AddTodo from "./components/AddTodo.vue"
import TodoHeader from "./components/TodoHeader.vue"
import Todos from "./components/Todos.vue"
import TodoFooter from "./components/TodoFooter.vue"

  export default {
    name: 'App',
    components: {
      TodoHeader,
      AddTodo,
      Todos,
      TodoFooter
     },
     data() {
       return {
         todos: [
          {
            id: 1,
            title: "Todo One",
            completed: false
          },
          {
            id: 2,
            title: "Todo Two",
            completed: true
          },
          {
            id: 3,
            title: "Todo Three",
            completed: false
          },
         ]
       }
     },

     
     methods: {
       // delete todo
       deleteTodo(id) {
        //  this.todos.todo.remove(todo => todo.id !== id)
         this.todos = this.todos.filter(todo => todo.id !== id)

       },

       // add-todo
       addTodo(newTodo) {
         this.todos = [...this.todos, newTodo];
       }
       
     },
}
</script>

<style scoped>

</style>