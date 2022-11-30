
<template>
    <MyBtn :color="color" >
      <template v-slot:icon>
        <span>(B)</span>
      </template>
      <template v-slot:text>
        <span>Banana</span>
      </template>
    
      </MyBtn>
    <!-- 문자 불러오기: -->
    <!-- log => h1 메소드  -->
    <MyBtn large color="royalblue">Banana</MyBtn>
    <MyBtn large>Banana</MyBtn>
    <MyBtn  @click="log" 
    
    class="asd" 
    style="color:red" 
    text="apple"
    @change-msg="logMsg"
    
    />
  <!-- logmsg는 하단에 참조 -->
  
    </template>
    
    <script>
    
    
    
    import MyBtn from './components/MyBtn.vue'
    export default{
  
    components:{
      MyBtn
      }
    ,
    data(){
        return{
            color:'#000'
        }
  
    }
  ,
  methods:{
    // lod -> h1 click method
           log(a)
           {
               console.log('a')
               console.log(a)
           },
           //log msg
           logMsg(msg){
           console.log(msg)
          }
  }
  }
    </script>
    
    
    <style>
    
    
    </style>