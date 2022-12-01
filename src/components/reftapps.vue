<template>
 <h1 @click="increase">
{{counr}}/{{doubleCount}}

 </h1>
 <h1>
{{message}}/{{reversedMessage}}

 </h1>
    </template>
    
    <script>
import { computed } from 'vue';

    export default{
        data(){
            return{
                message: 'Hello world',
                count:0

            },
            computed:{
                doubleCount(){
                    return this.count *2
                },
                reversedMessage(){

                    return this.message.split('').reverse().join('')
                }

            }

        }
     
    
    
    }
    </script>