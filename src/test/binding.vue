<template>
    <!-- isAtive 가 트루인지 아닌지 상태를 보며줌 -->
     <h1 
     :class="{active:isAtive}"
     @click="activate">
         heollo 바인딩
         {{isAtive}}
     </h1>
  </template>
  <script>
  export default {
    data(){
      return{    
        isAtive: false  
      }
    },
    methods:{
     
         // css 트루 펄스 를할당하여 css 적용
         activate()
         {
             this.isAtive= true
         }   
    }
  }
  </script>
  <style scoped>
  /* 해당뷰만 적용 scoped */

  .active{
    color: red;
    font-size:  bold;
  }
  </style>