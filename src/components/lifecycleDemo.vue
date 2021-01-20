<template>
  <div id="app">
    <h1>{{message}}</h1>
     <label for="message">請輸入訊息</label>
    <input type="text" v-model="message">
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Welcome to Vue!'
    };
  },
  methods: {
    doSomething() {
      alert('Hello!');
    }
  },
  beforeCreate(){
      alert("beforeCreated")
    console.log('beforeCreate called')
  },
  created() {
    console.log('created called')
  },
  beforeMount() {
    console.log('beforeMount called')
  },
  mounted() {
    console.log('mounted called')
  },
  beforeUpdate() {
      alert("beforeUpdate")
    console.log('beforeUpdate called')
  },
  updated() {
      alert("Updated")
    console.log('update called')
  }
};
</script>