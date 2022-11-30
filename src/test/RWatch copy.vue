<template>
    <h1 @click="changeMessage">
{{msg}}
    </h1>
    <h1>
        {{reversedMessage}}
    </h1>
    </template>

    <script>


    export default{
        data(){
            return {
                msg: 'halo'
            }
        },
   
    computed:{
            reversedMessage(){
                return this.msg.split('').reverse().join('')
            }

    },
    watch:{
msg(value){
    console.log('msg:',value)
},
reversedMessage(){
    console.log('msg:',this.reversedMessage)
}

    },
    methods: {
        changeMessage()
        {this.msg='Good!'}

    }
}
    </script>