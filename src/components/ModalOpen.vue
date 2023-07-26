<template>

  <div class="black-bg">
    <div class="white-bg">
      <img src="">
      <h4>title</h4>
      <p>price</p>
      <button @click="$emit('modalClose')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    props : {
      room: Array
    },
    methods: {
      onEmit(){
        this.$emit("ifopen", false);
      }
    }

}
</script>

<style scoped>
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
</style>