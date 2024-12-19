<template>
  <div id="app">
    <Navbar/>
    <heading/>
   <Home />
    
  </div>
</template>
<script>
import Home from "./components/Home.vue"
import Navbar from "./components/Navbar.vue";
import heading from "./components/heading.vue";
export default {
  components: {Home, Navbar, heading}
}
</script>
<style scoped>
*{
  margin:0;
  padding: 0;
  box-sizing: border-box;
}



</style>
