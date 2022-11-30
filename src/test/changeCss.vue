<template>
    <h1
      :style="[fontStyle, backgroundStyle]"
      @click="changeStyle() , changeStyle2()">
      Hello My name is Solyi
    </h1>
  <!-- 속성값고 스타일값이 같으면 생략가능 -->
    <h1
      :style="{
        color:color,
         fontSize: fontSize,
         backgroundColor
         }"
      @click="changeStyle2()">
      Hello My name is Solyi
    </h1>
  </template>
  <script>
//   fontStyle{normal : 보통 모양입니다.
// italic : 기울임꼴입니다.
// oblique : 기울임꼴입니다.
// initial : 기본값으로 설정합니다.
// inherit : 부모 요소의 속성값을 상속받습니다}
  export default {
    data(){
      return{ 
        color: 'red',
        fontSize: '20px',
        backgroundColor: 'green',
        fontStyle: {
          color:'orange',
          fontStyle: '30px'   
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
         changeStyle2(){
        this.color = 'grey',
        this.fontSize = '120px'
      
      }
    }
  }
  </script>
  