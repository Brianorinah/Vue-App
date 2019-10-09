<template>
  <div id="app">

      <Header/>
      <AddTodo v-on:add-todo="addTodo" />
      <Todos v-bind:todos="todos" v-on:delTodo="deleteTodo"/>
    
  </div>
</template>

<script>

import Todos from './components/todos';
import Header from './components/layout/header';
import AddTodo from './components/addTodo';
export default {
  name: 'app',
  components: {

    Header,
    Todos,
    AddTodo

    
  },
  data() {
    return{

      todos : []
    }    
     

  },

  methods : {

    deleteTodo(id){

      this.todos = this.todos.filter(todo => todo.id !==id);

    },

    addTodo(newTodo){

      this.todos = [...this.todos,newTodo];

    }
   },

   created : {

     
   }
}
</script>

<style>
*{
  
  box-sizing : border-box;
  margin: 0;
  padding: 0;

}

body{

  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn{

  display: inline-block;
  border: none;
  background: #555;
  color: #ffff;
  padding: 7px 20px;
  cursor:pointer;


}

.btn:hover {

  background : #666;



}

</style>
