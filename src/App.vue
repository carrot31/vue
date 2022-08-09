<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4 class="red" :style="스타일">{{product[0]}} 원룸</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{product[1]}} 원룸</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{product[2]}} 원룸</h4>
    <p>70 만원</p>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  //데이터 보관함(object형식으로)
  //데이터 바인딩 하는 이유: 
  //1. 하드코딩 시 후에 변경 어려움
  //2. vue의 실시간 자동렌더링 사용을 위해(data변경시 관련 HTML 자동 반영=> Web-app 사용 가능)
  //*자주 바뀔 일 없는 데이터의 경우엔 적용 x => 하드코딩
  //HTML 속성 데이터 바인딩: ':속성='데이터이름'
  data(){
    return{
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
  margin-top: 60px;
}
</style>
