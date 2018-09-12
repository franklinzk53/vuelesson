<template>
    <div :width="width+'px'">
      <Alert  type="error" show-icon >{{msg}}</Alert>
    </div>
</template>
<script>
import iView from 'iview';
  export default {
      components:{
        iView
      },
      data(){
         return {
             msg:"This is a alert msg 11"
            ,width:100
         }
      }
  }
</script>
