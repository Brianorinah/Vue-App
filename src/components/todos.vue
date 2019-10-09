<template>
  <div >
    <div v-bind:key="todo.id" v-for="todo in todos" >
    <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('delTodo',todo.id)"/>
        
    </div>
  </div>
</template>



<script>
import TodoItem from "./todoItem.vue";
export default {

    name: "Todos",
    components :{
            TodoItem

    },
    props : ["todos"]
 
}
</script>





<style>



</style>