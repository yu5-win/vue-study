<template>

  <div class="black-bg" v-if="modalopen==true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용<button @click="modalopen=false">닫기</button></p>
    </div>
  </div>

  <div class="menu">
    <a v-for="i in menus" :key="i">{{i}}</a>
  </div>

  <div v-for="(item,i) in onerooms" :key="i">
    <img :src="onerooms[i].image" class="room-img">
    <h4>{{onerooms[i].title}}</h4>
    <p>{{onerooms[i].price}}원</p>
  </div>
</template>

<script>
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return{
      onerooms : data,
      modalopen : false,
      report : [0, 0, 0],
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(){
      this.report[0]++;
    },
    increase1(){
      this.report[1]++;
    },
    increase2(){
      this.report[2]++;
    }
  },
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 200px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img{
  width: 100%;
  margin-top:40px;
}

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
