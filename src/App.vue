<template>
<h1 id="hello1">
  Hellow world!
</h1>

<h1 ref="hello">
  Hellow world!
</h1>
<Hello ref="hi"/>
</template>

<script>
import Hello from './components/Hello.vue'
export default{
components:{
  Hello
},
mounted(){

  const h1El = document.querySelector('#hello1')
  console.log(h1El.textContent)

  console.log(this.$refs.hello.textContent)

  console.log(this.$refs.hi.$refs.good)
 
}

}
</script>