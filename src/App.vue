<template>
  <nav>
    <router-link to="/">
      <figure>
        <img class="logomenu" alt="Churras logo" src="./assets/beef.png" />
      </figure>
    </router-link>
    <router-link to="/about">
      <img class="logomenu" alt="Churras logo" src="./assets/beer.png" />
    </router-link>
  </nav>
  <router-view />
</template>

<style>
body {
  background: #fafafa;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav {
  padding: 30px;
  background: #ffcd45;
  height: 8vh;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  text-align: center;
}
</style>
