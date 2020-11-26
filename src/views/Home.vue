<template>
  <div class="home">
    <div class="cta-container">
      <router-link class="block-link" to="/players">
        <div class="container">
          <div class="content">
            <img src="../assets/svg/man-user.svg" alt="icon joueur">
            <h2>Cliquez ici pour trouver des joueurs</h2>
          </div>
        </div>
      </router-link>
    </div>
    <div class="text-container">
      <img class="logo-main" src="../assets/img/controller.png" alt="Image d'accueil manette de jeux vidéos">
      <h1>Trouvez ou recrutez des joueurs</h1>
      <p>Marre de jouer en solo ? Ou vous souhaitez trouver des joueurs pour des parties amicales ou pour conquérir le classement de vos jeux en ligne préférés ? Découvrez maintenant le services Gameio et construisez votre chemin jusqu'à la gloire et la victoire. Ensemble.</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss" scoped>
  .home {
    h3 {
        font-size: 1.4rem;
        color: black;
        background-color: $block;
        color: white;
        text-align: center;
        padding: 20px;
        margin: 0;
        margin-bottom: 30px;
      }
    .text-container {
      img {
        width: 20%;
      }
      text-align: center;
      color: white;
      p {
        width: 60%;
        margin: auto;
      }
      padding: 20px;
      margin-bottom: 20px;
    }
    .cta-container {
      display: flex;
      flex-wrap: wrap;
      .block-link {
        text-decoration: none;
        width: 100%;
        height: 300px;
        background-image: url("../assets/img/home-bg.jpg");
        background-size: cover;
        .container {
          width: 100%;
          height: 100%;
          transition: .2s;
          background-color: rgba(41, 50, 65,.4);
          display: flex;
          justify-content: center;
          align-items: center;
          .content {
            text-align: center;
          }
        }
        .container:hover {
          background-color:$block;
        }
        img {
          width: 150px;
        }
        h2 {
          color:white;
        }
      }
    }
  }
  @media screen and (max-width:1024px) {
    .home {
      .cta-container {
        .left-block {
          width: 100vw;
        }
        .block {
          width: 100vw;
        }
      }
    }
  }
</style>