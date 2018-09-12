<template>
  <div id="app">
     <Button type="primary" @click="showMsg" >{{msg}}</Button>
  </div>
</template>
<script>
  export default {
      components:{

      },
      data(){
          return {
              msg:'Hello Button'
          }
      }
      ,methods:{
          showMsg() {
              alert(this.msg)
          }
    }
  }
</script>
