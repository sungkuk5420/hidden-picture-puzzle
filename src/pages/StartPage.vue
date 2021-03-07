<template>
  <q-page class="start-page flex flex-center">
    <div class="bg-1"></div>
    <div class="bg-2"></div>
    <div class="buttons-wrap">
      <div class="start-button button">Start</div>
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
  mounted(){
  }
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
    right:-8%;
    bottom:5%;
    width:50%;
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
    &:hover{
      transform: scale(1.1);
      cursor: pointer;
    }
  }
}
</style>