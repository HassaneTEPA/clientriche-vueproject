<template>
  <div class="admin">
    <h1>Gérer les utilisateurs et les équipes</h1>
    <h2>Joueurs</h2>
    <div v-if="!isEditing" class="players">
        <div class="player" v-for="(user, index) in users" :key="index">
            <h4>Prénom : {{user.firstname}}</h4>
            <h4>Nom : {{user.lastname}}</h4>
            <h4>Pseudo : {{user.nickname}}</h4>
            <h4>Jeux:</h4>
            <ul class="jeux">
                <li v-for="(game, index) in user.games"  :key="index">{{game}}</li>
            </ul>
            <button class="btn-del" @click="deletePlayer(user._id)">Supprimer le joueur</button>
            <button class="btn-edit" @click="editPlayer(user)">Modifier le joueur</button>
        </div>
    </div>
    <div v-if="isEditing" class="edit-players">
        <div class="player">
            <input type="text" v-model="updateNickname" placeholder="Pseudo">
            <input type="text" v-model="updateFN" placeholder="Prenom">
            <input type="text" v-model="updateLN" placeholder="Nom">
            <button @click="confirmEdit">Confirmer</button>
            <button @click="editPlayer">Annuler</button>
        </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Admin',
  components: {

  },
  data: function() {
      return {
          users:'',
          playersUrl:'http://localhost:3000/players',
          isEditing: false,
          updateNickname:'',
          updateFN:'',
          updateLN:'',
          playerBeingEdited: ''
      }
  },
  created:function() {
      axios.get(this.playersUrl)
        .then((res) => {
            this.users= res.data;
            console.log(this.users);
        })
        .catch((err) => {
            console.log(err);
        })
  },
  methods: {
        confirmEdit: function() {
            axios.put(this.playersUrl, {
                id: this.playerBeingEdited,
                nickname: this.updateNickname,
                firstName: this.updateFN,
                lastName: this.updateLN
            })
            .then((res) => {
                window.location.reload()
            })
            .catch((err) => {
                console.log(err)
            })
        },
        deletePlayer: function(id) {
            axios({
                method: 'delete',
                url: this.playersUrl,
                data: {
                    id: id
                }
            })
            .then((res) => {
                window.location.reload();   
            })
            .catch((err) => {
                console.log(err);
            })
        },
        editPlayer: function(player) {
            this.isEditing = !this.isEditing
            this.playerBeingEdited = player._id;
        }
  }
}
</script>

<style lang="scss" scoped>
    .admin {
        h1 {
            background-color: #7400b8;
            color: white;
            text-align: center;
            margin: 0;
            padding: 5px;
        }
        h2 {
            width: 80%;
            margin: 30px auto 30px auto;
        }
        color:white;
        .players {
            width: 80%;
            margin: auto;
            display: flex;
            flex-wrap: wrap;
            .player {
                background-color: $block;
                h3, h4 {
                    margin: 0;
                }
                padding: 20px;
                margin: 10px;
                width: 25%;
                border-left: 4px solid #7400b8;
                border-radius: 5px;
                .jeux {
                    p {
                        margin: 0;
                    }
                }
                .btn-del {
                    padding: 7px;
                    background-color: #ef233c;
                    color: white;
                    border: 2px solid #ef233c;
                    border-top-left-radius: 5px;
                    border-bottom-left-radius: 5px;
                    transition: .2s;
                    cursor: pointer;
                }
                .btn-edit {
                    padding: 7px;
                    background-color: #7400b8;
                    color: white;
                    border: 2px solid #7400b8;
                    border-top-right-radius: 5px;
                    border-bottom-right-radius: 5px;
                    cursor: pointer;
                }
            }
        }
        
    }
</style>