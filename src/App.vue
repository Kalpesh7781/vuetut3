<template>
  <!-- call the imported component here -->

  <!-- here we pass msg as a prop to child elment  -->
  <HelloWorld msg="Welcome to Your Vue.js App"/>


</template>

<script>
//import component here and then register those components 
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App', /*coponent name that we want to gave */
  components: {   /*coponent that we want to use in this copmponent */
    HelloWorld,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
