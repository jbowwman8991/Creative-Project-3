<template>
<div>
  <div class="intro">
    <h1 class="title">My Walls!</h1>
    <p>Here are your saved walls!</p>
  </div>
  <div class="container">
  </div>
  <MyWalls :walls="myWalls" />
</div>
</template>

<script>
import MyWalls from "../components/MyWalls.vue"
export default {
  name: 'Walls',
  components: {
    MyWalls
  },
  data() {
    return {
    }
  },
  computed: {
    myWalls() {
      return this.$root.$data.myWalls;
    }
  },
}
</script>

<style scoped>
.intro p {
  text-align: center;
  font-size: 20px;
}

.title {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 45px;
}

.container {
  display: flex;
  align-items: center;
  justify-content: center;
}

</style>
