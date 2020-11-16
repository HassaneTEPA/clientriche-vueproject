<template>
  <div class="players">
    <h1>Joueurs</h1>
    <h2>Dernier joueur</h2>
    <div class="recent-player">
        <div class="text">
            <h3>ASTRA Esport</h3>
        </div>
        <div class="logo">
            <img src="../assets/svg/man-user.svg" alt="Icon logo player">
        </div>
    </div>
    <h3>Tous les joueurs</h3>
    <div class="all-players">
        <div class="player">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="player">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="player">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="player">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
    </div>
    <h2></h2>
  </div>
</template>

<style lang="scss" scoped>
    .players {
        h1, h2, h3 {
            width: 90%;
            margin: auto;
            padding: 20px;
        }
        color: white;
        .recent-player {
            width: 80%;
            margin:auto;
            padding: 20px;
            border-radius: 10px;
            .text {
                margin-right: 300px;
                h3 {
                    font-size: 2.2rem;
                }
                .roster-head {
                    font-size: 1.3rem;
                }
                ul li {
                    font-size: 1.1rem;
                }
            }
            .logo {
                width: 200px;
            }
            display: flex;
            justify-content: center;
            background-color: #5390d9;
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
                background-color: #5390d9;
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