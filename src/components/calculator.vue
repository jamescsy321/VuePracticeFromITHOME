<template>
  <div class="flexbox">
    <div class="calculator">
      <input class="display" v-model="current"></input>
      <div class="btn dark" @click="clean">C</div>
      <div class="btn dark">+/-</div>
      <div class="btn dark">%</div>
      <div class="btn operator" @click="divided">/</div>
      <div class="btn" @click="append(7)">7</div>
      <div class="btn" @click="append(8)">8</div>
      <div class="btn" @click="append(9)">9</div>
      <div class="btn operator" @click="multiply">x</div>
      <div class="btn" @click="append(4)">4</div>
      <div class="btn" @click="append(5)">5</div>
      <div class="btn" @click="append(6)">6</div>
      <div class="btn operator" @click="minus">-</div>
      <div class="btn" @click="append(1)">1</div>
      <div class="btn" @click="append(2)">2</div>
      <div class="btn" @click="append(3)">3</div>
      <div class="btn operator" @click="plus">+</div>
      <div class="btn zero" @click="append(0)">0</div>
      <div class="btn" >.</div>
      <div class="btn operator" @click="equal">=</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      current: "",
      previous: "",
      operator: null,
      operatorClicked: false
    };
  },
  methods:{
      append(number){
          // 如果已點選任何運算子，則清空目前的值
          if(this.operatorClicked)this.current="";
           // 重置operatorClicked的值，讓第二個數字也能正常輸入
          this.operatorClicked=false;
          // 檢查目前值是否為0，如果不是的話就直接與current連接
          this.current = this.current ==="0" ?`${number}`:`${this.current}${number}`
      },
      plus(){
          this.operator =(a,b) =>a+b;
          this.setPrevious();
      },
      minus(){
          this.operator=(a,b) =>a-b;
          this.setPrevious();
      },
      multiply(){
          this.operator=(a,b) =>a*b;
          this.setPrevious();
      },
      divided(){
          this.operator=(a,b) =>a/b;
          this.setPrevious();

      },
      setPrevious(){
          // 將目前的值存在previous(按下個數字前要清空目前的current)
          this.previous = this.current;
          // 表示使用者確實按下任何一個運算子
          this.operatorClicked =true;
      },
      equal(){
          this.current=`${this.operator(parseFloat(this.previous),parseFloat(this.current))}`;
          this.operator=null;
          this.operatorClicked=false;
      },
      clean(){
          this.current ="0"
      }
  }
};
</script>

<style>  
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}  
  
.flexbox {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}
  
.calculator {
  display: grid;
  width: 300px;
  margin: 0 auto;
  font-size: 40px;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  border: .3px solid #868383;
  border-radius: 3rem;
  padding: .8em;
  background-color: #222;
}
  
.display {
  grid-column: 1/5;
  background-color: lightblue;
  text-align: right;
  padding-right: 20px;
  background-color: #D3D3D3;
  color: #333;
  margin-bottom: 10px;
  border-radius: 16px;
  outline: 0;
  font-size: 36px;
}
  
.btn {
  border: 1px solid black;
  background-color: #999;
  cursor: pointer;
  border-radius: 40px;
  margin: 10px;
  color: #222;
  font-weight: bold;
  text-align: center;
  transition: background-color 0.2s ease-in;
}
  
.btn:hover {
 background-color: #868383;   
}
.dark {
  background-color: #333;
  color: #ffffff;
}
.operator {
  background-color: #e08d1f;
}
.zero {
  grid-column: 1/3;
}
</style>