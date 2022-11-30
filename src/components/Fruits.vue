<template>
 
  <section >
    <button @click="add">aa</button>
    <h1>{{ReservMsg}}</h1>
  </section>
 

    <section v-if=" fruits.length > 0" >
        <h1>Fruits</h1>
            <ul>
              <li v-for="fruit in fruits" :key="fruit" >{{fruit +'과일'}}</li>
            </ul>
    </section>
    <section>
      <ul>
        <li v-for="fruitR in reversFruits" :key="fruitR">{{fruitR}}</li>
      </ul>
    </section>
</template>

<script>


export default {
  data() {
    return {
      ReservMsg:'hi',
      fruits: ['Apple', 'Banana', 'Cherry']
    }
  },
  //setter 연산가능
  methods:{
     add(){
      this.ReservMsgEvent += '?!'
    }
  },
  //computed: 캐싱데이터 연산한번하면 저장해둠 반복사용가능 getter 연산불가
  computed: {

    ReservMsgEvent:{
      get(){
        return this.ReservMsg
      }
      ,
    set(newValue)
        { // : 달린것은 역할setter 역할, 매개변수를 받아서 값 재설정 msg 를 newValue 로넣고 추가할수있는 소스를만듬
          this.ReservMsg = newValue
      }
      }
        ,
 
    hasFruit() {
      return this.fruit.length > 0
    },
    reversFruits(){
        return this.fruits.map(
          fruit=>{ 
            return fruit.split('').reverse().join('')
        }
        )

      

    }
  }
} 
</script>