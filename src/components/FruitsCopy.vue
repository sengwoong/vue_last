<template>
 
  <section >
    <button @click="add('hi',$event),handler()">aa2</button>
  </section>
  <section >
    <button @click="handler">aa</button>
  </section>
  

    <section v-if=" fruits.length > 0" >
        <h1>Fruits</h1>
            <ul>
              <li v-for="(fruit,index) in fruits" :key="fruit" >{{fruit +'과일'}}-{{index}}</li>
            </ul>
            <br/>
            <ul>
              <li v-for="(fruit) in FruitsIndex" :key="fruit.id" >{{fruit .name}}-{{fruit .id}}</li>
            </ul>
    </section>
    <br/>
    <section>
      <ul>
        <li v-for="fruitR in EFruits" :key="fruitR">{{fruitR}}</li>
      </ul>
    </section>
</template>

<script>
import shortid from 'shortid'

export default {
  data() {
    return {
      AddMsg:'개수가 증가',
      fruits: ['Apple', 'Banana', 'Cherry','test'],

    }
  },
  //setter 연산가능
  methods:{
     add(msg,event){
      this.AMsgEvent += '?!'
      console.log(msg)
      console.log(event)
    },
    handler(){
      this.fruits.push('Orange')

    }

  },
  //computed: 캐싱데이터 연산한번하면 저장해둠 반복사용가능 getter 연산불가
  computed: {
// 게터로 지정하면 한번 실행하고 클릭하면 다시또 받는다
    AMsgEvent:{
      get(){
        return this.AddMsg+'합니다'
      }
      ,
    set(newValue)
        { // : 달린것은 역할setter 역할, 매개변수를 받아서 값 재설정 msg 를 newValue 로넣고 추가할수있는 소스를만듬
          this.AddMsg = newValue
      }
      }
        ,
 
    hasFruit() {
      return this.fruit.length > 0
    },
    EFruits(){
        return this.fruits.map(
          fruit=>{ 
            return fruit + this.AMsgEvent
        }
        )
    },

//index 리스트렌더링
FruitsIndex(){
        return this.fruits.map(
          (fruit)=>{ 
            return {
              id:shortid.generate(),
              name:fruit
            }
        }
        )}
  }
} 
</script>