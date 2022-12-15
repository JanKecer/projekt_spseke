<template>
  <div>
    <h1 class="title">Counter App</h1>
    <div class="counter-container">
      <div class="box" v-on:click="minus()">-</div>
      <div v-if="counter!=0" class="box">{{counter}}</div>
      <div class="box" v-on:click="plus()">+</div>
    </div>
  </div>
</template>

<script setup>
let counter = ref(10)

const plus = ()=>{
  counter.value +=1
  console.log(counter)
}

const minus = ()=>{
  counter.value -=1
  console.log(counter)

}

</script>

<style>
  body{
    background-color: aquamarine;
    display: flex;
    justify-content: center;
  }
  .counter-container{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .box{
    width: 20%;
    background-color: blue;
    font-size: 20px;
    color: white;
    text-align: center;
  }

</style>
