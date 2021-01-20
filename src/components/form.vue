<template>
    <div class="form-container">
        <form>
        <h2>模擬送出表單</h2>
        <div class="input-group">
          <label for="username">請輸入帳號: </label>
          <input type="text" name="username" v-model="username">
        </div>
        <div class="input-group">
          <label for="username">請輸入密碼: </label>
          <input type="text" name="username" v-model="password">
        </div>
        <button @click.prevent="handleSubmit">送出</button>
      </form>
    </div>
        
</template>
<script>
export default {
    data() {
        return {
            message:'你好 我是Danny',
            textColor:'red',
            username:'',
            password:''
    };
  },
    methods: {
        handleSubmit(){
            alert(`你所輸入的帳號是: ${this.username} \n而你所輸入的密碼是${this.password}`)
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