<template>
  <div id="app">
     <MyLayout/>
  </div>
</template>
<script>
  import MyLayout from './components/MyLayout.vue'
  export default {
  name: 'app',
  components:{
    MyLayout
  },
  data () {
    return {


    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  /*margin-top: 60px;*/
}
li{
  text-align: left;
}
h1, h2 {
  font-weight: normal;
}

</style>
