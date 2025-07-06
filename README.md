Naruto-clicker.html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>Naruto/Boruto Clicker – Full Roster (1-100)</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; background: #111; color: #eee; margin: 0; padding: 20px;}
    h1 { color: #ffa726; }
    #enemy { width:300px; height:300px; margin:20px auto; background:#c62828;
      border-radius:10px; display:flex; justify-content:center; align-items:center;
      cursor:pointer; transition: transform .1s;}
    #enemy:active { transform: scale(.95); }
    #enemy img { max-width:100%; max-height:100%; border-radius:10px; }
    #info { margin-top:10px; font-size:20px; }
    #log { margin-top:20px; font-size:16px; color:#80deea; }
    #win { margin-top:30px; font-size:26px; color:#66bb6a; }
  </style>
</head>
<body>
  <h1>Naruto/Boruto Clicker – Full Roster (1-100)</h1>
  <div id="enemy" onclick="hitEnemy()"><img id="enemyImage" src="" alt="Ennemi"/></div>
  <div id="info"><div id="enemyName"></div><div id="enemyHP"></div></div>
  <div id="log"></div><div id="win"></div>

  <script>
    const enemies = [
      {name:"Naruto Uzumaki", hp:50, img:"https://i.imgur.com/kX1RaDZ.png"},
      {name:"Sasuke Uchiha", hp:60, img:"https://i.imgur.com/OQHEYY5.png"},
      {name:"Sakura Haruno", hp:40, img:"https://i.imgur.com/lvnDoLd.png"},
      {name:"Kakashi Hatake", hp:80, img:"https://i.imgur.com/Zx1v4lk.png"},
      {name:"Shikamaru Nara", hp:50, img:"https://i.imgur.com/tXyBf4A.png"},
      {name:"Rock Lee", hp:55, img:"https://i.imgur.com/21CQe8D.png"},
      {name:"Hinata Hyuga", hp:45, img:"https://i.imgur.com/ojtfFeA.png"},
      {name:"Neji Hyuga", hp:65, img:"https://i.imgur.com/Ct4C0Wx.png"},
      {name:"Might Guy", hp:120, img:"https://i.imgur.com/7SuE6iS.png"},
      {name:"Zabuza Momochi", hp:150, img:"https://i.imgur.com/0dpCFHT.png"},
      {name:"Haku", hp:160, img:"https://i.imgur.com/5uOQCGC.png"},
      {name:"Gaara", hp:180, img:"https://i.imgur.com/VvbhZK9.png"},
      {name:"Temari", hp:70, img:"https://i.imgur.com/WmX3T9p.png"},
      // … continue jusqu’à 100 personnages
    ];

    let currentEnemy = 0;
    let currentHP = enemies[currentEnemy].hp;

    function loadEnemy() {
      document.getElementById("enemyImage").src = enemies[currentEnemy].img;
      document.getElementById("enemyName").textContent = enemies[currentEnemy].name;
      document.getElementById("enemyHP").textContent = "Vie : " + currentHP;
      document.getElementById("log").textContent = "Clique pour attaquer !";
    }

    function hitEnemy() {
      currentHP--;
      document.getElementById("enemyHP").textContent = "Vie : " + currentHP;
      if (currentHP <= 0) {
        currentEnemy++;
        if (currentEnemy < enemies.length) {
          currentHP = enemies[currentEnemy].hp;
          document.getElementById("log").textContent = "✅ Ennemi vaincu ! Prochain combat...";
          setTimeout(loadEnemy, 1000);
        } else {
          document.getElementById("enemy").style.display = "none";
          document.getElementById("info").style.display = "none";
          document.getElementById("log").style.display = "none";
          document.getElementById("win").textContent = "🎉 Tu as vaincu les 100 premiers personnages !";
        }
      }
    }

    loadEnemy();
  </script>
</body>
</html>
