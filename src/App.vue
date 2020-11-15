<template>
  <div id="app">
    <div class="nav-container">
      <div class="logo">
        <span>GAMEIO</span>
      </div>
      <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
  body {
    margin: 0;
    padding: 0;
    background-color:#293241;
    font-family: 'Noto Sans', sans-serif;
    overflow-x: hidden;
  }
  #app {
    min-height: 100vh;
    width: 100vw;
  }
  .nav-container {
    color: white;
    list-style-type: none;
    display: flex;
    background-color: #ee6c4d;
    padding: 10px;
    a {
      color: white;
    }
    .logo {
      margin-right: 50px;
    }
  }
</style>
