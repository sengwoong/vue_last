<template>
  <h1>
  {{msg}}
  </h1>
  <h1>
    {{reserveMsg}}
  </h1>
  </template>
  
  <script>
  export default{
    data(){
      return{
        msg:'hello'
      }
    }
    ,
    methods:{
      changeMsg(){
      this.msg = 'Good!'}
  
    },
    watch:{
  
    },
    computed:{
      reserveMsg(){
        return this.msg.split(''),reseve(),jpin('')
      }
  
    }
  }
  
  </script>