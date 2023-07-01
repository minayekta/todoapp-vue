<template>
    <div :class="{ 'completed' : todoItem.completed }">
      <p @click="markComplete">{{ todoItem.title }}</p>
      <button @click="$emit('delete-todo-event', todoItem.id)">delete</button>
    </div>
</template>
  
  <script>
  
  export default {
     
  components: {
  },
  props: [
    "todoItem"
  ],
    methods: {
    markComplete(){
      this.todoItem.completed = !this.todoItem.completed
    },  
     addToDoItem(newToDoItem) {
      this.todoEntries = [...this.todoEntries, newToDoItem];
    },
    deleteToDoItem(toDoId){
      this.todoEntries = this.todoEntries.filter(item => item.id !== toDoId)
    }
  }, 
  }
  </script>
  <style>
      .completed {
        text-decoration: line-through;
      }
    </style>