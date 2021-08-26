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
import getPosts from '../composables/getPosts'

export default {
  components: { PostList },
  setup(){
    //composable function
    let {posts,error,load}=getPosts()

    load();
    
    return {posts,error};

    //destructring
    // let {name,age}={
    //   name:"aung ko ko khant",
    //   age: 19
    // }
    // console.log(age);
  }
}
</script>

<style>

</style>