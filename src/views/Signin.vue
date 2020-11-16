<template>
  <div class="signin">
    <div class="login-block form">
        <h1>Se connecter</h1>
        <form action="" method="post">
            <input class="inpt" type="text" placeholder="Nom d'utilisateur"><br/>
            <input class="inpt" type="password" placeholder="Mot de passe"><br/>
            <input class="btn btn-log" type="submit" value="Se connecter">
        </form>
    </div>
    <div class="sub-block form">
        <h1>S'inscrire</h1>
        <form action="" method="post">
            <input class="inpt" type="text" placeholder="Nom d'utilisateur"><br/>
            <input class="inpt" type="password" placeholder="Mot de passe"><br/>
            <input class="btn btn-signup" type="submit" value="S'inscrire">
        </form>
    </div>
  </div>
</template>

<style lang="scss" scoped>
    .signin {
        width: 90%;
        margin: auto;
        display: flex;
        justify-content: center;
        color: white;
        .login-block {
            width: 45%;
            background-color: #6930c3;
            padding: 20px;
            margin: 20px;
            border-radius: 10px;
        }
        .sub-block {
            width: 45%;
            background-color: #5390d9;
            padding: 20px;
            margin: 20px;
            border-radius: 10px;
        }
        .form {
            .inpt {
                font-size: .8rem;
                outline: none;
                padding: 10px;
                width: 250px;
                margin: 10px;
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
            }
            .btn:hover {
                cursor: pointer;
                background-color:white;
            }
            .btn-log {
                background-color:#6930c3;
            }
            .btn-log:hover {
                color: #6930c3;
            }
            .btn-signup {
                background-color: #5390d9;
            }
            .btn-signup:hover {
                color: #5390d9;
            }
        }
    }
</style>