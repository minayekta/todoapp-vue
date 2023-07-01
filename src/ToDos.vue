<template>
    <div>
        <h1> To Do List Vue </h1>
        <ul>
          <li :key="item.id" v-for="item in todoEntries" >
            <ToDoItem :todoItem="item" @delete-todo-event="$emit('delete-todo-event', item.id)"></ToDoItem>
          </li>   
      </ul>
    </div>
</template>
<script>
import ToDoItem from './components/ToDoItem.vue';
export default {
    components:{
    ToDoItem,
    },
    props:[
        "todoEntries"
    ],
   
}
</script>