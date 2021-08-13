<template>
  <div class="home">
    <input type="text" v-model="search">
    <p>Search Item - {{search}}</p>
    <div v-for="name in filteredNames" :key="name">
      {{name}}
    </div>
  </div>
</template>

<script>
import { computed, ref } from '@vue/reactivity'
export default {
  setup(){
    let search = ref("");
    let names = ref(["aungaung","kyawkyaw","susu","mgmg"]);

    let filteredNames=computed(()=>{
      return names.value.filter(name=>{
        return name.includes(search.value)
      })
    })

    return {names,search,filteredNames}
  }
}
</script>

<style>

</style>