<template>
  <div v-if="users.length > 0" class="players">
    <h1>Joueurs</h1>
    <h2>Dernier joueur</h2>
    <div class="recent-player">
        <div class="text">
            <h3>{{users[users.length - 1].nickname}}</h3>
            <p>Date : {{users[users.length - 1].createdAt}}</p>
            
        </div>
        <div class="logo">
            <img :src="users[users.length - 1].img" alt="Icon logo player">
        </div>
    </div>
    <h3>Tous les joueurs</h3>
    <div class="all-players">
        <div class="player" v-for="(user, index) in users" :key="index">
            <h4>{{user.nickname}}</h4>
            <p>Date d'inscription : {{user.createdAt}}</p>
            <p>Joue à</p>
            <ul>
                <li v-for="(game, index) in user.games" :key="index">{{game}}</li>
            </ul>
        </div>
    </div>
    <h2></h2>
  </div>
  <div v-else>
      <h1 style="color:white">Aucun joueur enregistré</h1>
  </div>
</template>
<script>
import axios from 'axios';

export default {
    data() {
        return {
            playersUrl:'http://localhost:3000/players',
            users: ''
        }
    },
    created: function() {
        axios.get(this.playersUrl)
        .then((res) => {
            this.users= res.data;
            console.log(this.users);
        })
        .catch((err) => {
            console.log(err);
        })
    }
}
</script>
<style lang="scss" scoped>
    .players {
        h1, h2, h3 {
            width: 90%;
            margin: auto;
            padding: 20px;
        }
        color: white;
        .recent-player {
            width: 65%;
            margin:auto;
            padding: 20px;
            border-radius: 10px;
            .text {
                margin-right: 300px;
                h3 {
                    font-size: 2.2rem;
                    padding-bottom: 0;
                }
                .roster-head {
                    font-size: 1.3rem;
                }
                ul li {
                    font-size: 1.1rem;
                }
                p {
                    padding: 20px;
                    margin-top: 0;
                }
            }
            .logo {
                width: 200px;
                img {
                    max-width: 200px;
                }
            }
            display: flex;
            justify-content: center;
            background-color: $block;
        }
        .all-players {
            display: flex;
            width: 90%;
            margin: auto;
            padding: 20px;
            border-radius: 10px;
            flex-wrap: wrap;
            justify-content: center;
            .player {
                h4, p {
                    margin: 8px;
                }
                background-color: $block;
                color: white;
                margin: 15px;
                padding: 12px;
                width: 400px;
                border-radius: 10px;
            }
        }
    }
    @media screen and (max-width:1024px) {
        .players {
            h1, h2, h3 {
                width: 100%;
                margin: auto;
                padding: 20px;
            }
            color: white;
            .recent-player {
                margin:auto;
                padding: 20px;
                border-radius: 10px;
                flex-wrap: wrap;
                .text {
                    margin-right: 0px;
                }
            }
            .all-players {
                .player {
                    width: 100%;
                }
            }
        }
    }
</style>