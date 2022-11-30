<template>
    <div
    class="btn"
    :class="{ large }"
    :style="{backgroundColor:color}"
    
    >
    <!-- slot 순서보장 -->
        <slot name = "icon">{{text}}
       </slot>
        <slot name = "text">{{text}}
       </slot>
    </div>
    
    <div
    :class="$attrs.class"
    :style="$attrs.style"
    >
    <slot>asd</slot>+ "2div"
    </div>
    
    
    <div
    v-bind="$attrs"
    >
    <slot></slot>+ "3div"
    </div>
    
    <!-- 에밋예제 -->
    <h1 @click="$emit('click',123)" >h1 click button method</h1>
    <input
    type="text"
    v-model="msg"
    />
    {{msg}}
    
    
    </template>
    
    
    
    
    <script>
    export default{
        data(){
            return{
                msg: ''
            }
        },
        watch:{
            msg(){
                this.$emit('changeMsg',this.msg)
            }
    
        },
       // inheritAttrs:false,
        //모든 스타일 적용안한기
    //상속하지않음 
    created(){
      console.log(this.$attrs)
    },
    //부모클래스에서 클릭이벤트 를 들고옴
    emits:[
    'click',
    
    //watch logmsg-> app.vue 연동
    'changeMsg'
     ],
    
    
      
        props:{
            color:{
                type:String,
                default:'gray'
            }
        ,
            large:{
                type: Boolean,
                default: false
        },
             text:{
                 type:String,
                 default:'????????'
        }},
        methods:{
            activate(text2)
             {
                 console.log(text2)
             }
        }
        
    }
    </script>
    <style scoped>
    .btn {
        display: inline-block;
        margin: 4px;
        padding: 6px 12px;
        border-radius:4px;
        background-color: gray;
        color: white;
        cursor: pointer;
    
    }
    .btn.large{
    font-size: 20px;
    padding: 10px 20px;
    
    }
    </style>