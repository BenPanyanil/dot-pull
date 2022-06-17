<template>
  <div id="app">
    <canvas id="canvas" :width="width" :height="height" style="border:2px solid #dddddd;"></canvas>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function () {
    return {
      width: 1000,
      height:500,

      pos_x: 100,
      pos_y: 100,
      radius: 20
    }
  },
  mounted: function () {
    // this.animation();
    requestAnimationFrame(this.draw)
  },
  methods: {
    animation: function () {
      requestAnimationFrame(this.draw);
    },
    draw: function () {
      const c = document.getElementById("canvas");
      const ctx = c.getContext("2d");

      ctx.clearRect(0, 0, this.width, this.height);

      ctx.beginPath();
      ctx.arc(this.pos_x, this.pos_y, this.radius, 0, Math.PI * 2);
      ctx.stroke();

      this.pos_x += 1

      requestAnimationFrame(this.draw)
    },  
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
  margin-top: 60px;
}
</style>
