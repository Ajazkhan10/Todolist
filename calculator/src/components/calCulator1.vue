<template>
  <h1>CalCulator</h1>
  <div class="calculator">
    <div class="display">{{current || '0'}}</div>
    <div @click="clear" class="btn">C</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percentage" class="btn">%</div>
    <div @click="divide" class="btn operator">/</div>
    <div @click="numberclick('7')" class="btn">7</div>
    <div @click="numberclick('8')" class="btn">8</div>
    <div @click="numberclick('9')" class="btn">9</div>
    <div @click="multiply" class="btn operator">x</div>
    <div @click="numberclick('4')" class="btn">4</div>
    <div @click="numberclick('5')" class="btn">5</div>
    <div @click="numberclick('6')" class="btn">6</div>
    <div @click="minus" class="btn operator">-</div>
    <div @click="numberclick('1')" class="btn">1</div>
    <div @click="numberclick('2')" class="btn">2</div>
    <div @click="numberclick('3')" class="btn">3</div>
    <div @click="add" class="btn operator">+</div>
    <div @click="numberclick('0')" class="btn zero">0</div>
    <div @click="dot" class="btn">.</div>
    <div @click="equal" class="btn operator">=</div>
  </div>
</template>
<script>
export default {
  name: "calCulator1",
  data(){
      return{
        current:'',
        previus:null,
        operator:null,
        opertorclicked:false
      }
  },
  methods:{
    clear(){
        this.current='';
    },
    sign(){
          this.current=this.current.charAt(0) === '-' ?
          this.current.slice(1): `-${this.current}`;
    },
    percentage(){
        this.current=`${parseFloat(this.current)/100}`
    },
    numberclick(number){
          if(this.opertorclicked){
         this.current='';
         this.opertorclicked=false;
         } 
        this.current=`${this.current}${number}`
    },
    dot(){
        if(this.current.indexOf('.') === -1){
            this.numberclick('.');
        }
    },
    setprevious(){
         this.previus=this.current;
         this.opertorclicked=true;
    },
    divide(){
       this.operator=(a,b)=>a/b;
       this.setprevious();
    },
    multiply(){
        this.operator=(a,b)=>a*b;
       this.setprevious();
    },
    minus(){
        this.operator=(a,b)=>a-b;
       this.setprevious();
    },
    add(){
       this.operator=(a,b)=>a+b;
       this.setprevious();
    },
    equal(){
     this.current=`${this.operator(
        parseFloat(this.current),
     parseFloat(this.previus)
     )}`;
    }
  }
};
</script>
<style scoped>
.calculator {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  height: 300px;
  justify-content: space-between;
  margin: auto;
}
.display {
  width: 100%;
  padding-top: 10px;
  font-size: 20px;
  font-weight: 500;
  height: 35px;
  background: blue;
  color: aliceblue;
  border: 2px solid black;
}
.btn {
  margin: 3px auto;
  border: 2px solid black;
  width: 70px;
  padding-top: 10px;
  background: rgb(4, 169, 190);
  color: aliceblue;
  font-size: 20px;
  font-weight: 600;
}
.btn:hover{
    background:rgb(109, 206, 219);
}

.zero {
  width: 146px;
}
.operator{
    background: orange;
    color: aliceblue;
}
.operator:hover{
    background: rgb(235, 179, 75);
}
</style>