<template>
 <!-- : = css 클래스부르기  // @ = 자바 클래스 들고오기 자바가 트루일떄 스타일적용 -->
    <h1 
    :class="{active:isAtive}"
    @click="activate">
        heollo 바인딩
        ({{isAtive}})
    </h1>
    
    
</template>
<script>
export default{
    data(){
        return {
            isAtive: false,
            color:red,
            fontSize:"30px",
       
        }
    },

    methods:{ 
        // css 트루 펄스 를할당하여 css 적용
        activate()
         {
             this.isAtive= true
         }
    }
}
</script>

