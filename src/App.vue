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

  <div v-for="(room,j) in oneroom" :key="room+j">
    <!-- HTML 태그안의 속성 데이터바인딩은 :~~
    HTMl 태그안의 내용 데이터바인딩은 {{~~}} -->
    <img :src='oneroom[j].image' class="room-img" @click="모달창열렸니 = true"/>
    <h4>{{oneroom[j].title}}</h4>
    <p>{{oneroom[j].price}}</p>
  </div>

</template>

<script>

import oneroom from './assets/oneroom';

export default {
  name: 'App',
  data(){
    return{
      //state
      모달창열렸니: false,
      신고수: [0,0,0],
      메뉴들:['Home','Shop','About'],
      product: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      oneroom: oneroom,
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
