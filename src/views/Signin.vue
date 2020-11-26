<template>
  <div class="signin">
    <div class="login-block form">
        <h1>Se connecter</h1>
        <form @submit="handleLogin">
            <div class="inpt-grp">
                <input v-model="playerLoginUsn" class="inpt" type="text" placeholder="Nom d'utilisateur">
                <input v-model="playerLoginPwd" class="inpt" type="password" placeholder="Mot de passe">
            </div>
            <p class="err">{{errMsg}}</p>
            <input class="btn" :class="{'btn-log': !canLog}" type="submit" :disabled="canLog" value="Se connecter">
        </form>
    </div>
    <div class="sub-block form">
        <h1>S'inscrire</h1>
        <form @submit="handleSub">
            <div class="inpt-grp">
                <input v-model="playerSubUsn" class="inpt" type="text" placeholder="Nom d'utilisateur">
                <input v-model="playerSubPwd" class="inpt" type="password" placeholder="Mot de passe">
                <input v-model="playerSubLN" class="inpt" type="text" placeholder="Nom">
                <input v-model="playerSubFN" class="inpt" type="text" placeholder="Prénom">
                <input v-model="playerSubImg" class="inpt" placeholder="Optionnel : Lien vers une image" type="text">
                <div class="check-container">
                    <h3>Jeux :</h3>
                    <label for="lol">League of legends</label>
                    <input @change="handleCheck" type="checkbox" name="lol" id="lol" value="League of Legends">
                    <label for="cod">Call of Duty</label>
                    <input @change="handleCheck" type="checkbox" name="cod" id="cod" value="Call of Duty">
                    <label for="wow">World of Warcraft</label>
                    <input @change="handleCheck" type="checkbox" name="wow" id="wow" value="World of Warcraft">
                </div>
            </div>
            <input class="btn" :class="{'btn-signup': !canSub}" :disabled="canSub" type="submit" value="S'inscrire">
        </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
// pour pouvoir voir le panel admin, se connecter avec : Nom d'utilisateur : admin & Mot de passe : admin
export default {
  name: 'Signin',
  data: function() {
    return {
        playerSubUsn:'',
        playerSubPwd:'',
        playerSubFN:'',
        playerSubLN:'',
        playerSubImg:'',
        playerLoginUsn:'',
        playerLoginPwd:'',
        playerSubGames:[],
        loggedIn: false,
        userSession:'',
        errMsg:''
    }
  },
  computed: {
      canLog: function() {
          if (this.playerLoginUsn.length > 0 && this.playerLoginPwd.length > 0) {
              return false;
          } else {
              return true;
          }
      },
      canSub: function() {
          if (this.playerSubUsn && this.playerSubPwd && this.playerSubFN && this.playerSubLN) {
              return false;
          } else {
              return true;
          }
      }
  },
  methods: {
      handleSub: function(event) {
          event.preventDefault();
          axios.post('http://localhost:3000/signup', {
              usn: this.playerSubUsn,
              pwd: this.playerSubPwd,
              firstName: this.playerSubFN,
              lastName : this.playerSubLN,
              img: this.playerSubImg,
              games: this.playerSubGames
          })
            .then((res) => {
                alert("Merci de votre inscription!");
                this.clear();
            })
            .catch(function(err) {
                alert(err);
            })
      },
      handleLogin: function(event) {
          event.preventDefault();
          axios.post('http://localhost:3000/signin', {
              usn: this.playerLoginUsn,
              pwd: this.playerLoginPwd
          })
            .then((res) => {
                if (res.data == "admin") {
                    window.location.href = "#/admin";
                } else if (res.data != false) {
                    alert("Bienvenue " + res.data[0].nickname);
                    this.clear();
                } else {
                    this.errMsg = "Votre nom d'utilisateur ou votre mot de passe est incorrect"
                }
            })
            .catch(function(err) {
                console.log(err);
            })
      },
      handleCheck: function(event) {
          if (event.target.checked === true) {
              this.playerSubGames.push(event.target.value);
          } else {
              this.playerSubGames.splice(this.playerSubGames.indexOf(event.target.value),1);
          }
      },
      clear: function() {
        this.playerSubUsn=''
        this.playerSubPwd=''
        this.playerSubFN=''
        this.playerSubLN=''
        this.playerSubImg=''
        this.playerLoginUsn=''
        this.playerLoginPwd=''
        this.playerSubGames=[]
      }
  }
}
</script>

<style lang="scss" scoped>
    .signin {
        width: 90%;
        margin: auto;
        display: flex;
        justify-content: center;
        color: white;
        flex-wrap: wrap;
        align-items: flex-start;
        .err {
            font-size: .8rem;
        }
        .login-block {
            width: 40%;
            background-color: $block;
            padding: 20px;
            margin: 20px;
            border-radius: 5px;
        }
        .sub-block {
            width: 40%;
            background-color: $block;
            padding: 20px;
            margin: 20px;
            border-radius: 5px;
        }
        .form {
            .inpt-grp {
                display: flex;
                flex-wrap: wrap;
                .check-container {
                    height: 100%;
                    width: 100%;
                }
            }
            .inpt {
                font-size: .8rem;
                outline: none;
                padding: 10px;
                width: 40%;
                margin: 10px;
                border: 0px;
                border-radius:5px;
            }
            .btn {
                font-size: .8rem;
                outline: none;
                padding: 10px;
                width: 130px;
                margin: 10px;
                color: white;
                border:1px solid white;
                transition: .2s;
                border-radius:5px;
            }
            .btn-log {
                background-color:$block;
            }
            .btn-log:hover {
                color: $block;
                cursor: pointer;
                background-color:white;
            }
            .btn-signup {
                background-color: $block;
            }
            .btn-signup:hover {
                color: $block;
                cursor: pointer;
                background-color:white;
            }
        }
    }
    @media screen and (max-width:1024px) {
        .signin {
            .form {
                width: 100%;
                .inpt {
                    width: 90%;
                }
            }
        }
    }
</style>