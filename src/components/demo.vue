<template>
    <div id="app" v-bind:class="[activeClass, errorClass]">
        <h1>{{message}}</h1>
        <button @click="greet">Click Me</button>
        <p v-if="isLogin">登入</p>
        <p v-else>未登入</p>

        <p v-show="isAdmin">管理員</p>
        <button @click="isAdmin=!isAdmin">切換身分</button>
        <ul>
            <li v-for="(todo, index) in todos" :key="todo.id">{{index}}{{todo}}</li>
        </ul>
        <ul>
            <li v-for="(value,key) in person" :key="value.id" >{{key}} : {{value}}</li>
        </ul>

        <!-- v-model -->
        <h1 :style={color:textColor}>{{msg}}</h1>
        <input type="text" v-model="msg" >

        <input type="text" name="username" v-model="username" v-focus>



        <!-- <img :src="imgSrc" alt="image"> -->
    </div>
        
</template>
<script>
export default {
    data() {
        return {
            message:'Welcome to Vue',
            imgSrc:'https://wonderfulengineering.com/wp-content/uploads/2016/01/Desktop-Wallpaper-2.jpg',
            activeColor: 'red',
            fontSize: 30,
            activeClass: 'active',
            errorClass: 'text-danger',
            isAdmin:false,
            isLogin:true,
            todos: ["Learn vue","Buy diner", "Make a todo list"],
            person: {
                        name:'Danny',
                        age: 29,
                        gender: 'male'
                    },
                    msg:'v-model測試',
                    textColor:'red'
            
    }
  },
    methods: {
        greet() {
            alert("hello world")
        }
    },
    directives:{
        focus:{
            inserted:function(el){
                el.focus()
            }
        }
    }
}
</script>
<style>

</style>