<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <router-view/> -->
    <!-- <Demo></Demo>
    <Form></Form> -->
    <!-- <Calculator></Calculator> -->
    <!-- <ComputedDemo></ComputedDemo> -->
    <!-- <LifeCycle></LifeCycle> -->
    <ToDoList></ToDoList>
    <!-- <NewToDoList></NewToDoList> -->
  </div>
</template>

<script>
import Demo from './components/demo'
import Form from './components/form'
import Calculator from './components/calculator'
import ComputedDemo from './components/computedDemo'
import LifeCycle from './components/lifecycleDemo'
import ToDoList from './components/todoList'
import NewToDoList from './components/newTodoList'

export default {
  name: 'App',
  components:{ 
    Demo,
    Form,
    Calculator,
    ComputedDemo,
    LifeCycle,
    ToDoList,
    NewToDoList
  }
  

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
