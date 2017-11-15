<template>
<div>
  <section class="hero is-large v-carousel" ref="v-carousel">
    <div class="hero-body v-items-container">
      <img v-for="(image,$index) in images" :src="image" :style="'transform: rotateY(' + (($index+cursor)*deg) + 'deg ) translateZ(' + translatez + 'px )'" ></figure>
    </div>
  </section>
  
  <a class="button is-warning is-hovered" @click="++cursor">+</a>
  <a class="button is-danger is-hovered" @click="--cursor">-</a>
</div>
</template>

<script>
export default {
  name: 'carousel',
  data () {
    return {
      images : [
        "./src/assets/logo.png",
        "./src/assets/1.png",
        "./src/assets/2.png",
        "./src/assets/3.png"
      ],
      panelSize: 0,
      translatez: 0,
      degrees: 360,
      deg: 0,
      cursor: 0
    }
  },
  methods:{
    loadTransitionZ: function (){

      this.panelSize = this.$refs["v-carousel"].clientWidth;
      
      this.deg = Math.round(this.degrees/this.images.length)
      
      this.translatez = Math.round( ( this.panelSize / 2 ) / Math.tan( Math.PI / this.images.length ) );

      console.log(this.panelSize);
    }
  },
  mounted: function(){
    this.loadTransitionZ();
  }
}
</script>

<style>
.v-carousel{
  box-shadow: 2px 2px 2px 2px #DEDEDE;
}

.v-carousel .v-items-container{
  transform-style: preserve-3d;
}

.v-carousel  .v-items-container img{
  margin: 0;
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0px;
  top: 0px;
  border: 2px solid black;
}
</style>
