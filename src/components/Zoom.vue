<template>
  <div class="zoom">
    <img ref="original"
      id="original"
      src="@/assets/poster.jpg" 
      alt="An awsome poster of The Legend of Zelda: The Wind Waker"
      @mouseenter="hover = true"
      @mousemove="setLensPosition($event)"
      @mouseleave="hover = false">
    <div v-show="hover" ref="zoom" id="lens" />
  </div>
</template>

<script>
export default {
  name: 'Zoom',
  data() {
    return {
      hover: false
    }
  },
  methods: {
    setLensPosition(e) {
      let x = parseInt(e.layerX - 125)
      let y = parseInt(e.layerY - 125)
      let style = this.$refs.zoom.style
      style.left = `${x}px`
      style.top = `${y}px`
      style.backgroundImage = `url(${e.target.src})`
      style.backgroundPosition = `${-(Math.floor(x * 2))}px ${-(Math.floor(y * 2))}px`
      style.backgroundSize= `auto ${Math.floor(parseInt(e.target.height) * 2 - 250)}px`
    }
  },
}
</script>

<style scoped>
.zoom {
  position: relative;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
#original {
  position: initial;
  z-index: 0;
  border: 1px solid black;
  max-height: 95%;
}
#lens {
  position: absolute;
  z-index: 1;
  background-color: #2c3e50;
  border: 1px solid black;
  width: 250px;
  height: 250px;
  pointer-events: none;
  background-repeat: no-repeat;
}
</style>
