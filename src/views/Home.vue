<template>
  <div class="home">
      <div v-if="error">
          {{error}}
      </div>

      <div v-if="posts.length>0">
        <PostList :posts = "posts"></PostList>
      </div>
      <div v-else>
          loading.......
      </div>
    
    
  </div>
</template>

<script>
import PostList from '../components/PostList'
import { ref } from '@vue/reactivity'
export default {
  components: { PostList },
  setup(){
    
    let posts= ref([]);
    let error=ref("");

    let load=async()=>{
      try{

        let response = await fetch("http://localhost:3000/posts")
        if(response.status===404){
          throw new Error("not found Url");
        }
        let datas = await response.json()
          posts.value=datas
      }catch(err){
        // console.log(error.message)
        error.value=err.message;
      }
    }

    load();
    
    return {posts,error}
  }
}
</script>

<style>

</style>