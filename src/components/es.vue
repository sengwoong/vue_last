<template>

    <!-- isAtive 가 트루인지 아닌지 상태를 보며줌 -->
     <h1 
     :class="{active:isAtive}"
     @click="activate">
         heollo 바인딩
         ({{isAtive}})
     </h1>


    <h1
      :style="[fontStyle, backgroundStyle]"
      @click="changeStyle">
      Hello My name is Solyi
    </h1>

<!-- 속성값고 스타일값이 같으면 생략가능 -->


    <h1
      :style="{
        color:color,
         fontSize: fontSize,
         backgroundColor
         }"
      @click="changeStyle2">
      Hello My name is Solyi
    </h1>

<button @click="VIfHandler">

  <!-- v-if html 에남아있지않음 랜더링 하지않음(처음부터) 전환비용이높다 show는 초기비용이낮다-->
  <h1 v-if="VIfHandlerData">
1
</h1>
<h1 v-else-if="VIfHandlerCount > 3">
2
</h1>
<h1 v-else>
3
</h1>
</button>
 

  </template>
  
  <script>
  export default {
    data(){
      return{ 
        VIfHandlerCount:0,
        VIfHandlerData:true,
        isAtive: false,
        color: 'red',
        fontSize: '20px',
        backgroundColor: 'green',
        fontStyle: {
          color:'orange',
          fontStyle: '30px'   ,
           
        },
        backgroundStyle:{
          backgroundColor: 'black'
        }
      }
    },
    methods:{
      changeStyle(){
        this.fontStyle.color = 'grey',
        this.fontStyle.fontSize = '120px'
      
      }
      ,
         // css 트루 펄스 를할당하여 css 적용
         activate()
         {
             this.isAtive= true
         },
         changeStyle2(){
        this.color = 'grey',
        this.fontSize = '120px'
      
      },
      VIfHandler(){
        this.VIfHandlerData =!this.VIfHandlerData,
        this.VIfHandlerCount += 1
        if (this.VIfHandlerCount == 5){
          this.VIfHandlerCount = 0

        }
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