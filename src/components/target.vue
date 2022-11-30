<template>
<a
href="https://naver.com"
target="_blank"

@click.prevent.once="handler"
>
<!-- prevent 동작안함 -->

    Naver
</a>



<div
class="parent"
@click="handlerA">
<div
class="child1"
@click="handlerB"
>
<div
class="child2"
@click.self="handlerC"
>
<!-- self 는 자기자신 클릭인됌 stop 은 부모가 클릭이안됌  -->
<div
class="child3"
@click.stop="handlerD"
>
</div>
</div>
</div>
</div>


<div
class="parent"
@click.capture.stop="handlerRA">
<div
class="child1"
@click="handlerRB"
>
</div>
</div>

<div
class="parent2"
@wheel.passive="handlerA">
<!-- passive스크롤독입 -->
<div
class="child01"
@click="handlerA"
>
</div>
</div>


</template>

<script>
export default{
    methods:{
        handler(event){
            // html 이벤트금지
            event.preventDefault()
            console.log(event.target)
            console.log(event.currentTarget)
            // 위 html @click.self 는 event.target(이벤트 지정한값) == event.currentTarget(현재선택된상황 (가장앞)) 이같을떄 동작한다.
            console.log('abc!')
        },
        handlerA(){
            console.log('a')
        }
        ,
        handlerB(event){
            event.stopPropagation()
            console.log('b')
        }
        ,
        handlerC(){
            console.log('c')
        }
        ,
        handlerD(){
            console.log('d')
        }


        ,
        handlerRA(){
            console.log('a')
        }
        ,
        handlerRB(){
            
            console.log('b')
        }
        ,
        handlerRC(){
            console.log('c')
        }
        ,
        handlerScroll(event){
            for (let i = 0; i <10000; i++)
            {
                console.log(event)

            }

        }

    }


}
</script>
<style scoped lang="scss">
.parent{
width: 300px;
height: 300px;
background-color: aqua;
margin: 10px;
padding: 10px;
    .child1{
        width: 100px;
        height: 100px;
        margin: 5px;
        padding: 5px;
        background-color: beige;

    
        .child2{
            width: 80px;
            height: 80px;
            background-color: blue;
            .child3{
            width: 50px;
            height: 50px;
            background-color: red;

     }
     }
    }
 
  
}

.parent2{
width: 300px;
height: 300px;
background-color: aqua;
margin: 10px;
padding: 10px;
overflow: auto;
.child01{
            width: 80px;
            height: 2000px;
            background-color: blue;}

}

</style>