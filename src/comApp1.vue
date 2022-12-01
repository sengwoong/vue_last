<template>
    <Myttn
    class="heropy"
    style="color:red"
    color="#ff0000"
    @hello="log"
    >
    Apple
    </Myttn>
</template>
<script>
import MyBtn from './comBtn1.vue'
export default{
    components:{
        MuBtn
    },
    methods:{
        log(){
            console.log('HelloWorld')
        }
    }

}
</script>