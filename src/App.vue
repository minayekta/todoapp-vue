<template>
   <ToDos :todoEntries="todoEntries" />

  <AddToDoButton @add-todo-event="addToDoItem"/>


</template>

<script>
import ToDos from './ToDos.vue'

export default {
  name: 'App',
  components: {
    ToDos
  },
  data(){
    return{
      todoEntries: [
        {
          id: 1,
          title: 'go to shoping',
          compelted: false
        },
         {
          id: 2,
          title: 'go to home',
          compelted: false
        },
        {
          id: 3,
          title: 'go to ...',
          compelted: false
        }
      ]
    }
  },
  methods:{
    addToDoItem(newToDoItem) {
      this.todoEntries = [...this.todoEntries, newToDoItem];
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
