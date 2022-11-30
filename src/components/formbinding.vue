<template>
    <h1>{{msg}}</h1>
    <h1>{{msg2}}</h1>
    <h1>{{msg3}}</h1>
    <!-- change 는 나가거나 엔터누르면 변함 인풋은 바로번함 -->
    <input type="text" :value="msg" @change="handler"/>
    <input type="text" :value="msg2" @input="msg2 = $event.target.value.trim()"/>
    <input type="text" v-model.lazy.number.trim="msg3"  />
    <!-- v-model 체크박스 한글은안됌 -->
</template>
<script>
export default{
data(){
    return{
        msg: 'hihihi',
        msg2: 'hihi2',
        msg3: '3333'
    }

},
methods:{

    handler(event){
       
        console.log(event.target.value)
        this.msg = event.target.value.trim()
    }
},
watch:{
    msg3() {
     console.log(typeof this.msg3)
    }
    
}

}


</script>