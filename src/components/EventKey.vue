<template>
<input
type="text"
@keydown="handler"/>
<input
type="text"
@keydown.ctrl.shift.enter="handler2"/>
</template>
<script>
export default{
methods:
{
    handler(event){
        if(event.key==='Enter'){
            console.log('Enter!!')
        }
    },
    handler2(){
        
            console.log('Enter!!')
        
}

}}
</script>