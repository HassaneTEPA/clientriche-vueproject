<template>
  <div class="home">
    <div class="text-container">
      <h1>Trouvez une équipe ou recrutez des joueurs</h1>
      <p>Marre de jouer en solo ? Ou vous souhaitez trouver des joueurs pour des parties amicales ou pour conquérir le classement de vos jeux en ligne préférés ? Découvrez maintenant le services Gameio et construisez votre chemin jusqu'à la gloire et la victoire. Ensemble.</p>
    </div>
    <div class="cta-container">
      <div class="block">
        <div class="content left">
          <div class="container">
            <img src="../assets/svg/man-user.svg" alt="icon joueur">
            <h2>Trouvez une équipe</h2>
          </div>
        </div>
      </div>
      <div class="block">
        <div class="content right">
          <div class="container">
            <img src="../assets/svg/teamwork.svg" alt="icon joueur">
            <h2>Trouvez des joueurs</h2>
          </div>
        </div>
      </div>
    </div>
    <h3>Créer, Gérer, Trouver, Jouer.</h3>
    <div class="infos">
      <div class="info-text-container">
        <div class="item">
          <img src="../assets/svg/man-user.svg" alt="icon joueur">
          <h4>Créer une équipe</h4>
          <p>Créez votre équipe sur Gameio afin de faciliter la gestion de celle-ci et profitez de tous nos services gratuitement.</p>
        </div>
        <div class="item">
          <img src="../assets/svg/man-user.svg" alt="icon joueur">
          <h4>Gérer une équipe/des joueurs</h4>
          <p>Gérer son équipe n'a jamais été aussi facile. Ajoutez, supprimez et cherchez des joueurs grace à nos outils de gestion.</p>
        </div>
        <div class="item">
          <img src="../assets/svg/man-user.svg" alt="icon joueur">
          <h4>Trouver des joueurs</h4>
          <p>Vous souhaitez trouver de nouveaux membres pour votre équipe ou vous cherchez simplement de nouveaux camarades pour vos parties amicales en ligne ? GAMEIO met à votre disposition tous les outils dont vous avez besoin.</p>
        </div>
      </div>
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
        background-color: #ee6c4d;
        color: white;
        text-align: center;
        padding: 20px;
        margin: 0;
        margin-bottom: 30px;
      }
    .text-container {
      text-align: center;
      color: white;
      h1 {

      }
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
      .block {
        width: 50vw;
        height: 40vh;
        background-image: url('../assets/img/home-bg.jpg');
        background-size: cover ;
        background-repeat: no-repeat;
        cursor: pointer;
        .left:hover {
            background-color: #ee6c4d;
            transition: .2s;
          }
          .right:hover {
            background-color: #ee6c4d;
            transition: .2s;
          }
        .content {
          transition: .2s;
          background-color: rgba(41, 50, 65,.4);
          width: 100%;
          height: 100%;
          .container {
            img {
              width: 10%;
            }
            h2 {
              margin: 0;
              padding: 0;
            }
            position: relative;
            top: 30%;
            color: white;
            text-align: center;
          }
        }
      }
    }
    .infos {
      width: 90%;
      margin: auto;
      text-align: center;
      .info-text-container {
        display: flex;
        justify-content: center;
        .item {
          margin: 20px;
          width: 33%;
          color: white;
          img {
            width: 13%;
          }
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