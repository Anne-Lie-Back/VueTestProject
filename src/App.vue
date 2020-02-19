<template>
  <div id="app">
    <Header/>
    <ShoppingList/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ShoppingList from './components/ShoppingList.vue'

export default {
  name: 'App',
  components: {
    Header,
    ShoppingList,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  /*background: #FFF177;*/
  background-image: url("./assets/pencilBG.jpg");
  background-size: cover;
  width: 100%;
  height: 100vh;
}
</style>
