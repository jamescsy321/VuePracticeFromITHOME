<template>
  <div id="app">
    <label for="firstname">Firstname</label>
    <input type="text" name="firstname"  v-model="firstName">
    <label for="lastname">Lasttname</label>
    <input type="text" name="lastname" v-model="lastName">
    <h2>{{fullName}}</h2>

    <label for="firstname">Firstname</label>
    <input type="text" name="person.name"  v-model="person.name">
    
    
    
  </div>
</template>

<script>
export default {
  data() {
    return {
         firstName: 'Danny',
      lastName: 'Wang',
      person:{
          name:'Danny',
          id:100000
      }
    };
  },
  methods: {
    getFullName() {
      
      return `${this.firstName} ${this.lastName}`
    }
  },
  computed: {
    fullName() {
        
      return this.firstName + ' ' + this.lastName
    }
  },
  watch: {
    //   firstName:function(val,oldVal){
    //       console.log(`the firstName has been change,the new value is ${val}`)
    //     console.log(`the oldVal is ${oldVal}`)
    //   },
    firstName:{
        handler(val,oldVal){

        },
        immediate:true,
        deep:true
    },
      
      "person.name":function(val){
          console.log(` value is ${val}`)
      }
  }
};
</script>