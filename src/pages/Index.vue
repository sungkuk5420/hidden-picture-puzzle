<template>
  <q-page class="flex flex-center">
    <div
      class="bg"
    ></div>
    <div class="character" v-for="(item,index) in count" :key="index" :ref="'character'"> </div>
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
    console.log(this.$refs.character1)
    for (let index = 0; index < this.count;index++) {
      const element = this.$refs.character[index];
      const maxWidth = window.innerWidth/100-1;
      const maxheight = window.innerHeight/100-3;
      
    let widthRandom =Math.floor(Math.random() * Math.floor(maxWidth))+1;
    let heightRandom =Math.floor(Math.random() * Math.floor(maxheight))+3;
    let leftPosition = 67 *index;
    let topPosition = 66.5 *index;
    let alreadyPosition = this.hasPosition.filter(item=>item.x == widthRandom && item.y == heightRandom)[0];
    while(alreadyPosition){
      widthRandom =Math.floor(Math.random() * Math.floor(12))+1;
      heightRandom =Math.floor(Math.random() * Math.floor(6))+3;
      alreadyPosition = this.hasPosition.filter(item=>item.x == widthRandom && item.y == heightRandom)[0];
    }
    
    this.hasPosition = [...this.hasPosition,{x:widthRandom,y:heightRandom}];
      element.style.top=heightRandom+"00px";
      element.style.left=widthRandom+"00px";
      element.style.backgroundPosition=`${leftPosition}px ${topPosition}px`;
    }
  }
}
</script>

<style lang="scss">
.bg{
  width:100%;
  height: 100vh;
  background: #bee7ff;
  background-image: url("~assets/ground.png");
  background-repeat: no-repeat;
  background-size:cover;
}
.character{
  position: absolute;
  background-image: url("~assets/characters.png");
  width:67px;
  height:66.5px;
  
}
</style>