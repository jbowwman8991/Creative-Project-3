<template>
<div>
  <div class="intro">
    <h1 class="title">User Finder</h1>
    <p>Search here to find your favorite user and the walls that they have added!</p>
  </div>
  <div class="container">
    <div>
      <img src="images/search--v1.png">
    </div>
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" placeholder="Username"/>
      </form>
    </div>
  </div>
  <UserWalls :walls="walls" />
</div>
</template>

<script>
import UserWalls from "../components/UserWalls.vue"
export default {
  name: 'Home',
  components: {
    UserWalls
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    walls() {
      return this.$root.$data.walls.filter(wall => wall.username.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
}
</script>

<style scoped>
.intro p {
  text-align: center;
  font-size: 20px;
  padding-left: 30px;
  padding-right: 30px;
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

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 30px;
}

img {
  padding: 10px 10px;
  width: 40px;
}

</style>
