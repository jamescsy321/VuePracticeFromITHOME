<template>
     <div :class="[todo.isComplete? 'success':'error','todo-wrapper']">
      <div class="todo-title">
        {{todo.title}}
      </div>
      <div class="todo-icons">
        <i class="fa fa-check" aria-hidden="true" @click="completeTodo"></i>
        <i class="fa fa-trash-alt" aria-hidden="true" @click="deleteTodo"></i>
      </div>
    </div>
        
</template>
<script>

export default {
    data() {
        return {
            todos:todos
    }
  },
   props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods:{
    deleteTodo(){
      this.$emit('delete-todo',{
        title:this.todo.title
      })
    },
    completeTodo(){
      this.$emit('finish-todo',{
        title:this.todo.title
      })
    }
  }
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}

.fa-trash-alt {
  color: red;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
}

.fa-check {
  color: green;
  margin-right: 5px;
}

.todo-wrapper {
  display: flex;
  justify-content: space-between;
  border-radius: 16px;
  box-shadow: 5px 0 5px rgba(0, 0, 0, 0.3);
  width: 270px;
  padding: 1.5rem 0.8rem;
  margin-top: 0.3rem;
}

.todo-title {
  font-size: 18px;
  font-weight: bold;
}

.todo-icons {
  display: flex;
  cursor: pointer;
}

.success {
  border-left: 4px solid green;
}

.error {
  border-left: 4px solid red;
}
</style>