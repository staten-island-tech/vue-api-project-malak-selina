<template>
  <div id="app">
    <div id="nav">
      <router-link to="/list">
      <img src="./assets/logo.png" alt="Logo" class="logo">
      </router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.logo{
  width:12vw;
  margin:0 auto;
  float: left;
  z-index: 10;
  position:fixed;
}

</style>
