<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos :todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos'
import Header from './components/layout/header'
import AddTodo from './components/AddTodo'

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data(){
    return {
      todos: []
    }
  },
  methods:{
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos.push(newTodo)
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0px;
    padding: 0px;
  }

  body{
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    line-height: 1.4;
    text-align: center;
  }

  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover{
    background: #666;
  }
</style>
