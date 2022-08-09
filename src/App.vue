<template>

  <div class="menu">
    <!-- 1. 자료안의 데이터 갯수만큼 반복됨 -->
    <!-- 2. 작명한 변수는 데이터안의 자료가 됨 -->
    <!-- key 용도: 반복문 사용시 구분하기 위해 사용 -->
    <!-- i는 1씩 증가하는 변수 -->
    <a v-for="(tag,i) in 메뉴들" :key="tag+i">{{tag}}</a>
  </div>

  <div>

    <div v-for="(room, j) in product" :key="room+j">
    <h4>{{room}}</h4>
    <p>50 만원</p>
    </div>
    
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      메뉴들:['Home','Shop','About'],
      product: ['역삼동원룸', '천호동원룸', '마포구원룸']
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
