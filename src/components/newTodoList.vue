<!-- Use preprocessors via the lang attribute! e.g. <template lang="pug"> -->
<template>
  <div id="app">
    <h1>My Todo List</h1>
    <div :class="[todos[0].isComplete ? 'success' : 'error', 'todo-wrapper']">
      <div class="todo-title">
        {{ todos[0].title }}
      </div>
      <div class="todo-icons">
        <i class="fa fa-check" aria-hidden="true"></i>
        <i class="fa fa-trash-alt" aria-hidden="true"></i>
      </div>
    </div>
  </div>
</template>

<script>
const todos = [
  {
    title: "Get dressed",
    isComplete: false
  },
  {
    title: "Buy food",
    isComplete: false
  },
  {
    title: "Eat lunch",
    isComplete: true
  },
  {
    title: "Write Article",
    isComplete: true
  }
];

export default {
  data() {
    return {
      message: "Welcome to Vue!",
      todos: todos
    };
  },
  methods: {}
};
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
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
  magrin-top: 0.3rem;
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
