<template>

  <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a) in 메뉴들 " :key="a">{{a}}</a>
  </div>


  <div v-for="(a, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창 = true">{{ 원룸들[i].title }}</h4>
    <p> {{ 원룸들[i].price }}</p> 
  </div> 
</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return{
      원룸들  : data,
      메뉴들 : ['Home', 'Shop', 'About'],
      모달창 : false
    }
  },
  methods : {
    increase(i){
      this.신고수[i] += 1;
    }
  }, 
  components: {
  }
}
</script>

<style>
body{
  margin : 0
}

div{
  box-sizing: border-box;
}

.black-bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white-bg{
  width:100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
