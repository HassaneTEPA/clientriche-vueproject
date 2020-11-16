<template>
  <div class="teams">
    <h1>Equipes</h1>
    <h2>Dernière equipe</h2>
    <div class="recent-team">
        <div class="text">
            <h3>ASTRA Esport</h3>
            <ul>
                <span class="roster-head">Joueurs:</span>
                <li>Kurri</li>
                <li>Harwil</li>
            </ul>
        </div>
        <div class="logo">
            <img src="../assets/svg/man-user.svg" alt="Icon logo team">
        </div>
    </div>
    <h3>Toutes les équipes</h3>
    <div class="all-teams">
        <div class="team">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="team">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="team">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
        <div class="team">
            <h4>Nom d'équipe</h4>
            <p>5 membres</p>
        </div>
    </div>
    <h2></h2>
  </div>
</template>

<style lang="scss" scoped>
    .teams {
        h1, h2, h3 {
            width: 90%;
            margin: auto;
            padding: 20px;
        }
        color: white;
        .recent-team {
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
            background-color: #6930c3;
        }
        .all-teams {
            display: flex;
            width: 90%;
            margin: auto;
            padding: 20px;
            border-radius: 10px;
            flex-wrap: wrap;
            justify-content: center;
            .team {
                h4, p {
                    margin: 8px;
                }
                background-color: #6930c3;
                color: white;
                margin: 15px;
                padding: 12px;
                width: 400px;
                border-radius: 10px;
            }
        }
    }
    @media screen and (max-width:1024px) {
        .teams {
            h1, h2, h3 {
                width: 100%;
                margin: auto;
                padding: 20px;
            }
            color: white;
            .recent-team {
                margin:auto;
                padding: 20px;
                border-radius: 10px;
                flex-wrap: wrap;
                .text {
                    margin-right: 0px;
                }
            }
            .all-teams {
                .team {
                    width: 100%;
                }
            }
        }
    }
</style>