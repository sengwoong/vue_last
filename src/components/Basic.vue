
<template>
<Fruits/>

  <!--    v-once = 1번만실행 -->
  <!-- <h1 
    v-once 
    @click="add">
    {{ msg }}
  </h1> -->

  <h1 
    @click="add">
    {{ msg1 }}
  </h1>

  <h1 v-html="msg2" ></h1>
  <h1 v-bind:class=" msg3">{{msg3}}</h1>

  <!--   attr->data 에있는 class 라고적은것을 들고옴 event 도같은원리 -->
  <h1 
  :[attr]="'active'"
  @[event]="add3">
  {{msg3}}</h1>
</template>

<script>
import FruitsVue from './components/Fruits.vue'
export default{
data(){
return{
  msg1:'hi', 
  msg2:'<div style ="color:red;">hihihi </div>',
  msg3: 'active',
  attr : 'class',
  event : 'click'

}
},

methods: {

  add(){
    this.msg1 += '!'
  },
  add3(){
    this.msg3 += '!'
  }
}
  

}
</script>


<style>
/* msg3 클래스 */
.active{
color: blue;
font-size: 100px;

}
</style>