<template>
    <div @click ="increase">
    {{count}}
    </div>
    
    </template>
    
    <script>
    import {ref,computed,watch,onMounted} from 'vue'
    export default{
    setup(){
      const count = ref(0)
  
    function increase(){
    count +=1
    
    }
    
  const doubleCount =computed(()=> {return this.count.value *2})
  
  watch(msg,(newValue)=>{console.log(newValue)})
  
  const msg = ref('helloworld')
    function chanfeMassage(){
  msg ='good'
    
    }
  
  
    const reversedMessage = computed(()=>{return this.message.value.split('').reverse().join('')})
  console.log(msg.value)
  //created 는 정의하지않음
  
   onMounted(()=>{console.log(count.value)})
  
    return{
        count,
        increase,
        doubleCount,
  
        msg,
        chanfeMassage,
  
        reversedMessage
    }
    
    }
    
    }
    </script>