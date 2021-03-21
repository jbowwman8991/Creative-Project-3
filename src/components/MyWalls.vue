<template>
<div class="container">
  <div class="walls">
    <div class="wall" v-for="wall in walls" :key="wall.id">
      <div class="info">
        <h1>{{wall.address}}</h1>
        <h1>{{wall.city}}</h1>
        <p>{{wall.state}}</p>
      </div>
      <div class="bottom">
        <h2>Username:
        {{wall.username}}</h2>
        <h2>Date Added:
        {{wall.date}}</h2>
        <button class="auto" v-on:click='removeWall("wall.id" - 1)'>Remove Wall</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'WallList',
  props: {
    walls: Array
  },
  methods: {
    removeWall(location) {
      this.$root.$data.myWalls.splice(location, 1);
    }
  },
}
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.walls {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.wall {
  margin: 10px;
  margin-top: 50px;
  width: 375px;
}

.info {
  background: #ADD8E6;
  padding: 5px 15px;
  height: 150px;
}

.info h1 {
  font-size: 25px;
}

.info p {
  margin: 0px;
  font-size: 18px;
}

.bottom {
  display: flex;
  align-items: center;
}

.bottom h2 {
  font-size: 20px;
  padding: 5px 15px;
}

button {
  height: 50px;
  background: #00255F;
  color: white;
  border-radius: 20px;
}

.auto {
  margin-left: auto;
}

/* Mobile Styles */
@media only screen and (max-width: 767px) {

}

/* Tablet Styles */
@media only screen and (min-width: 768px) and (max-width: 960px) {

}

/* Desktop Styles */
@media only screen and (min-width: 961px) {
  .wall {
    width: 375px;
  }
}

</style>
