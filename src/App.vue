<template>
<div id="app">
  <div id="menu">
    <div id="logo">
      <router-link to="/">
        <img src="/images/wallball.jpg">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/">
        <div class="menu-item">
          <img src="/images/stick.png">
          <p>HOME</p>
        </div>
      </router-link>
      <router-link to="/user">
        <div class="menu-item">
          <img src="/images/plus.png">
          <p>USERS</p>
        </div>
      </router-link>
      <router-link to="/walls">
        <div class="menu-item">
          <img src="/images/wall.png">
          <p>MY WALLS</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="footer">
    <p>View all code <a href="https://github.com/jbowwman8991/Creative-Project-3" target="blank">HERE</a></p>
  </div>
</div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

#app {
  background-color: #e6f3f8;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "side logo none";
  margin-bottom: 50px;
  padding: 10px;
}

#logo {
  grid-area: logo;
  display: flex;
  justify-content: center;
  padding-top: 120px;
}

#logo img {
  height: 250px;
  border: solid 1px black;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-first;
}

#side img {
  height: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px 5px;
}

.menu-item p {
  margin: 0px;
  text-align: center;
  color: black;
  text-decoration: underline;
}

.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  background-color: #ADD8E6;
}

/* Mobile Styles */
@media only screen and (max-width: 767px) {

}

/* Tablet Styles */
@media only screen and (min-width: 768px) and (max-width: 960px) {

}

/* Desktop Styles */
@media only screen and (min-width: 961px) {
  body {
    width: 900px;
  }
}
</style>
