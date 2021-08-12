<template>
  <div class="home">
    <h1>Home Page</h1>
    <p>Hello {{name}}. I am {{age}} years old</p>

    <input type="text" v-model="name">
    <button @click="handleclick"> Click</button>
    <button @click="age++">increae age</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
// @ is an alias to /src


export default {
  setup(){
    let name = ref("AKKK");
    let age = ref(20);
    let handleclick =()=>{
      name.value="kyaw kyaw";
    }
    return {name,age,handleclick}
  }
}
</script>
