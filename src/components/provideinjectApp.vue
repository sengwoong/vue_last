<template>
  <!-- <Parent :msg="msg"/>  -->
  <Parent/>

  </template>
  <script>
import Parent from './components/Parent.vue'
import {computed} from 'vue'
export default{
components:{
  Parent
},
data(){
  return{
   
    msg: 'asdasd'
  }
},
// 계산된데이터
computed:{
   
  msg: 'asdasd'
}
,
// provide 는 일반이게반응성이없음 컴퓨티드랑 같이 만들어야 반응성이있음 
provide(){
  return{

    // promsg: this.msg 이렇게 만들면 반응성이없음

    promsg: computed(()=>{
      return this.msg
    })

    // promsg: computed(()=>this.msg)

  }
  

}


}
  </script>