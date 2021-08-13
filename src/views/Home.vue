<template>
  <div>
    <!-- <h1>Person One</h1>
    <p>{{personOne.name}}-{{personOne.age}}</p>
    <button @click="changeOne">Change One</button>

    <h1>Person Two</h1>
    <p>{{personTwo.name}}-{{personTwo.age}}</p>
    <button @click="changeTwo">ChangeTwo</button> -->
    <h1>UserOne-{{userOne}}</h1>
    <h1>UserTwo-{{userTwo}}</h1>
  </div>
</template>

<script>
import { reactive, ref } from '@vue/reactivity'
export default {
  setup(){
    // let personOne = ref({name:"kyawkyaw",age:30});
    // let changeOne=()=>{
    //   personOne.value.name="Change kyawKyaw"
    // }

    // let personTwo =reactive({name:"MGMG",age:30});
    // let changeTwo=()=>{
    //   personTwo.name="change mgmg"
    // }

    // return {personOne,changeOne,personTwo,changeTwo}

    let userOne = ref("AKKK");
    let userTwo = reactive("MGMG");
    let changeOne=()=>{
      userOne.value= "Change abc";
    }

    return {userOne,userTwo,changeOne}
  }
}
</script>

<style>
  
</style>