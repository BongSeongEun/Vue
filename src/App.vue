<template>

  <div class="menu">
    <a v-for="naming in menu" :key="naming">{{ naming }}</a>
  </div>

  <!-- <div class="black-bg" v-if="ifopen == true">
    <div class="white-bg">
      <img src="">
      <h4>{{room[0].title}}</h4>
      <p>{{room[0].price}}</p>
      <button @click="ifopen = false">닫기</button>
    </div>
  </div> -->
  
  <ModalOpen v-bind:state="ifopen"/>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      신림역 원룸
    </button>
    <img src="./assets/room0.jpg"/>
    <p>{{room[0].price}}</p>
    <button @click="report[0]++">허위매물신고</button><br>
    <span>신고수: {{report[0]}}</span>
  </div>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      창동 원룸
    </button>
    <img src="./assets/room1.jpg"/>
    <p>{{room[1].price}}</p>
    <button @click="report[1]++">허위매물신고</button><br>
    <span>신고수: {{report[1]}}</span>
  </div>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      금산 아파트
    </button>
    <img src="./assets/room2.jpg"/>
    <p>{{room[2].price}}</p>
    <button @click="report[2]++">허위매물신고</button><br>
    <span>신고수: {{report[2]}}</span>
  </div>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      더블베드 아파트
    </button>
    <img src="./assets/room3.jpg"/>
    <p>{{room[3].price}}</p>
    <button @click="report[3]++">허위매물신고</button><br>
    <span>신고수: {{report[3]}}</span>
  </div>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      명글 아파트
    </button>
    <img src="./assets/room4.jpg"/>
    <p>{{room[4].price}}</p>
    <button @click="report[4]++">허위매물신고</button><br>
    <span>신고수: {{report[4]}}</span>
  </div>

  <div class="main">
    <button class="modal" @click="ifopen = true">
      반지하 원룸
    </button>
    <img src="./assets/room5.jpg"/>
    <p>{{room[5].price}}</p>
    <button @click="report[5]++">허위매물신고</button><br>
    <span>신고수: {{report[5]}}</span>
  </div>



</template>

<script>
  import oneroom from './data/oneroom.js';
  import ModalOpen from './components/ModalOpen.vue'
  oneroom;
  export default{
    name: 'App', 
    components: {
      ModalOpen
    },
    data(){
      return{
        menu : ['Home', 'Shop', 'About'],
        products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
        prices : ['50', '60', '70'],
        report : [0,0,0,0,0,0],
        room : oneroom,
        ifopen : false,

      }
    }
  }
</script>

<style>
img{
  width: 100%;
  margin-top: 40px;
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
  margin-top: 10px;
}
.main{
  margin-top: 5px;
}
</style>
