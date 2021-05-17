<template>
  <div id="app">
    <img src="./assets/logo.png">
    <listView @myMsg="getData"></listView>
    <HeaderView :msg="title"></HeaderView>
  </div>
</template>

<script>
import ListView from './components/List'
import List from './components/List.vue'
import HeaderView from './components/Header.vue'

export default {
  name: 'App',
  components: {
    ListView,
    HeaderView
  },
  data(){
    return {
      title: "vue入門"
    }
  },
  methods: {
    getData(msg){
      console.log("在app.vue組件"+ msg);
      // this.title = msg;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
