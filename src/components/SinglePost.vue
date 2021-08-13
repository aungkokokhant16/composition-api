<template>
  <h2>{{post.title}}</h2>
  <p>{{cupPostBody}}</p>
</template>

<script>
import { computed } from '@vue/reactivity'
export default {
    props:['post'],
    setup(props){
        let cupPostBody = computed(()=>{

            return props.post.body.substring(0,100)+"......";
        })

        return {cupPostBody}
    }
}
</script>

<style>

</style>