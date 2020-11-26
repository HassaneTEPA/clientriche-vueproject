<template>
  <div id="app">
    <div class="nav-container">
      <div class="logo">
        <span>GAMEIO</span>
      </div>
      <div id="nav">
        <div class="content">
          <router-link to="/">Accueil</router-link>
          <router-link to="/players">Joueurs</router-link>
          <router-link to="/signin">Se connecter/S'inscrire</router-link>
        </div>
      </div>
      <div class="hamburger" @click="handleClick">
          &#9776;
      </div>
      <div v-if="hamburgerActive" class="mobile-nav">
        <h1>GAMEIO</h1>
        <router-link to="/">Accueil</router-link>
        <router-link to="/players">Joueurs</router-link>
        <router-link to="/signin">Se connecter/S'inscrire</router-link>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hamburgerActive: false
    }
  },
  methods: {
    handleClick: function() {
      this.hamburgerActive = !this.hamburgerActive;
    }
  }
}
</script>

<style lang="scss">
  body {
    margin: 0;
    padding: 0;
    background-color:$background;
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
    background-color: $block;
    padding: 10px;
    a {
      color: white;
      padding: 10px;
      margin: 5px;
    }
    .logo {
      margin-right: 50px;
      width: 20%;
    }
    #nav {
      width: 80%;
      text-align: right;
      a {
        text-decoration: none;
      }
    }
    .mobile-nav {
      display: none;
    }
    .logo-mobile {
      display: none;
    }
    .hamburger {
      display:none;
    }
  }
  @media screen and (max-width:1024px) {
    .nav-container {
      display: block;
      padding: 0;
    }
    .hamburger {
        display: block !important;
        width: 100%;
        height: 100%;
        text-align: center;
        cursor: pointer;
        padding: 10px 0 10px 0;
    }
    #nav {
      display: none;
      .content {
        display: none;
      }
    }
    .logo {
      display: none;
    }
    .mobile-nav {
      display: flex !important;
      align-items: flex-start;
      flex-direction: column;
      justify-content: center;
      a {
        text-decoration: none;
      }
    }
  }
</style>
