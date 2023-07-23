<template>

  <div class="menu">
    <a v-for="naming in menu" :key="naming">{{ naming }}</a>
  </div>

  <div class="main"
    v-for="name,i in products" :key="i">
    <button class="modal" @click="ifopen = true">
      {{ name }}
    </button>

    <p>**만원</p>
    <button @click="report[i]++">허위매물신고</button>
    <span>신고수: {{report[i]}}</span>
    <button @click="ifopen = false">닫기</button>
  </div>

  <div class="black-bg" v-if="ifopen == true">
    <div class="white-bg">
      <img src="">
      <h4>{{room[0].title}}</h4>
      <p>{{room[0].price}}</p>
    </div>
  </div>

</template>

<script>
  import onerooms from './data/oneroom.js';
  export default{
    name: 'App', 
    data(){
      return{
        menu : ['Home', 'Shop', 'About'],
        products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
        prices : ['50', '60', '70'],
        report : [0,0,0],
        ifopen : false,
        room : onerooms,
      }
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
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color : white;
  padding: 10px;
}
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.modal{
  background: transparent;
  border: transparent;
  font-size: 18px;
  font-weight: bold;
}
.main{
  margin-top: 5px;
}
</style>
