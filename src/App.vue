<template>
  <MyBtn
  class="heropy"
  style= "color: red;"
  color="#ff0000"
  @hello="log"
  >
  Apple
  </MyBtn>
</template>
<script>
import MyBtn from './comBtn1.vue'
export default{
  components:{
      MyBtn
  },
  methods:{
      log(){
          console.log('HelloWorld')
      }
  }

}
</script>