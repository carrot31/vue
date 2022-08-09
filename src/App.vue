<template>

  <div class="menu">
    <a v-for="(tag,i) in 메뉴들" :key="tag+i">{{tag}}</a>
  </div>

  <div>
    <h4 >{{product[0]}} 원룸</h4>
    <p>50 만원</p>
    <!-- ctrl+spacebar: 다양한 기능확인가능 -->
    <!-- 함수사용가능 -->
    <button @mouseover="increase(0)">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
    
  </div>
  <div>
    <h4>{{product[1]}} 원룸</h4>
    <p>70 만원</p>
    <button @mouseover="increase(1)">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <h4>{{product[2]}} 원룸</h4>
    <p>70 만원</p>
    <button @click="increase(2)">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      신고수: [0,0,0],
      메뉴들:['Home','Shop','About'],
      product: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods:{
    increase(a){
      // 함수 사용시 this.필수
      this.신고수[a]++
    },
    decrease(){
      this.신고수--
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
  }
</style>
