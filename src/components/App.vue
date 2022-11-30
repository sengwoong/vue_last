<template>
  <Parent :msg="message"/>
<button
:class="size"
@click="clickLog"
>sss</button>
  </template>
  <script>
import Parent from './components/Parent.vue'
export default{
  components:{


},
data()
{
return{
  message:'HelloWorld'
}
},
computed:{
clickLog (){
    console.log(message)
}

}

}


  </script>

  <style>
.size{
  width: 3000px;
  height: 3000px;
}
</style>