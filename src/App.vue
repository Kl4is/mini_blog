<template>
  <div class="bg-gray-500 flex flex-col min-h-screen">
    <Header></Header>
    <div class="flex-1 flex w-2/3 mx-auto p-4 text-lg bg-white h-full shadow-lg">
      <div class="w-3/5">
        <router-view :key="$route.fullPath" />
      </div>
      <div class="w-2/5">
        
        <LatestPosts/>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "@/components/site/header/Header.vue"

import LatestPosts from "@/components/blog/LatestPosts.vue"
  export default{
    data(){
      return{
        selectedSort:''
      }
      
    },
    components: {
      Header,
      LatestPosts,
    
    }
  };
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
