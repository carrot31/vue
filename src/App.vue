<template>

  <div class="black-bg" v-if="모달창열렸니 == true" >
    <div class="white-bg" >
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(tag,i) in 메뉴들" :key="tag+i">{{tag}}</a>
  </div>

  <div>
    <!-- img 절대경로는 그냥 넣기 -->
    <!-- 상대경로는 asset폴더 ./로 시작 -->
    <img src='./assets/room0.jpg' class="room-img" @click="모달창열렸니 = true"/>
    <h4>{{product[0]}} 원룸</h4>
    <p>50 만원</p>
    <!-- ctrl+spacebar: 다양한 기능확인가능 -->
    <!-- 함수사용가능 -->
    <button @mouseover="increase(0)">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
    
  </div>
  <div>
    <img src='./assets/room1.jpg'/>
    <h4>{{product[1]}} 원룸</h4>
    <p>70 만원</p>
    <button @mouseover="increase(1)">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src='./assets/room2.jpg'/>
    <h4>{{product[2]}} 원룸</h4>
    <p>70 만원</p>
    <button @click="decrease(2)">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
  </div>
  
</template>

<script>
// 동적인 UI만드는법:
// 0. UI디자인
// 1. UI의 현재 상태를 데이터로 저장해둠
// 2. 데이터에 따라 UI가 어떻게 보일지 작성(v-if='조건식')

export default {
  name: 'App',
  data(){
    return{
      //state
      모달창열렸니: false,
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
    decrease(b){
      this.신고수[b]--
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
.room-img{
  width: 100%;
  margin-top: 40px;
}
.black-bg{
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
