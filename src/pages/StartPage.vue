<template>
  <q-page class="start-page flex flex-center">
    <img src="~assets/mouse.png" alt="" srcset="" class="cursor" draggable="false">
    <div class="bg-1"></div>
    <div class="bg-2"></div>
    <div class="buttons-wrap">
      <div class="start-button button" draggable="false">Start</div>
    </div>
    <img src="~assets/anpanman-run.gif" class="anpanman-run">
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data(){
    return {
      count:56,
      hasPosition:[]
    }
  },
}
</script>

<style lang="scss">
// 第一引数で基準となる画面幅のフォントサイズ、第二引数で基準となる画面幅を入力
@function get_vw($size, $viewport:320){
  $rate: 100 / $viewport;
  @return $rate * $size * 1vw;
}

@mixin fz_vw($font_size:10){
  font-size: $font_size * 1px;
  font-size: get_vw($font_size);
}
.start-page{
  overflow: hidden;
  .bg-1{
    background:#FDDFE9;
    opacity: 1;
    width:100%;
    height:100vh;
    position: absolute;
    z-index: -1;
  }
  .bg-2{
    width:100%;
    height:100vh;
    position: absolute;
    background-image:url("~assets/bg-icon.png");
    background-size:10%;
    opacity: 0.2;
    z-index: -1;
  }
  .anpanman-run{
    position: absolute;
    right:-6%;
    bottom:5%;
    width:35%;
    max-width:600px;
  }
  .button{
    display: flex;
    justify-content: center;
    align-items: center;
    @include fz_vw(13);
    padding: 1vw 10vw;
    border: get_vw(5) solid #D32F2F;
    border-radius: 15px;
    color: #F44336;
    background: #FFCDD2;
  }
}

@import url('https://fonts.googleapis.com/css?family=Anton');

.cursor {
  left: 0;
  top: 0;
  width: get_vw(30);
  height:  get_vw(30);
  min-width:100px;
  min-height:100px;
  position: absolute;
  border-radius: 5px;
  z-index: 1;
}

.cursor__follower {
  transition: transform .4s;
  width: 6px;
  height: 6px;
}

/* Unrelated styles */
html {
  cursor: none;
  background-color: #2d2b2b;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

h1 {
  font-family: 'Anton', 'helvetica', sans-serif;
  font-size: 100px;
  letter-spacing: 12px;
  line-height: 1;
  text-align: center;
}

h1 span {
  letter-spacing: 15px;
}
</style>