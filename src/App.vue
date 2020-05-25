<template>
  <div id="app">
    <div id="nav">
      <NavBar/>
    </div>
    <div class="body">
      <router-view/>
    </div>
    
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
export default {
  components:{
    NavBar
  }
}
</script>

<style scoped>
.body{
  width: 80%;
  margin: auto;
  padding: 0.5rem;
}
</style>

