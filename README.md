# liza-love-situ
Лиза я люблю тебе 
<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<title>Любиш Лізу?</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: #111;
        color: white;
        text-align: center;
        overflow: hidden;
    }

    #main {
        margin-top: 100px;
    }

    h1 {
        font-size: 42px;
    }

    button {
        padding: 15px 35px;
        font-size: 22px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-weight: bold;
        position: relative;
    }

    .yes {
        background: #28d628;
    }

    .no {
        background: #d62828;
        position: absolute;
        transition: top 0.05s, left 0.05s; /* ультрабыстро */
    }

    img {
        margin-top: 20px;
        width: 300px;
        border-radius: 12px;
    }
</style>
</head>
<body>

<div id="main">
    <h1>Ти любиш Лізу?</h1>

    <button class="yes" onclick="yes()">ДА</button>

    <button id="noBtn" class="no"
        onmouseover="runAway()"
        ontouchstart="runAway()">НЕТ</button>
</div>

<div id="result" style="display:none;">
    <h1 id="text"></h1>
    <img id="image" src="">
</div>

<audio id="music"></audio>

<script>
function yes() {
    document.getElementById("main").style.display = "none";
    document.getElementById("result").style.display = "block";

    document.getElementById("text").innerText = "Молодець! Ти любиш Лізу ❤️";
    document.getElementById("image").src = "https://i.imgur.com/yJxwN5U.jpeg";

    let music = document.getElementById("music");
    music.src = "https://www.dropbox.com/scl/fi/oz0m7ibc5vblmt36d9yse/happy-cat.mp3?dl=1";
    music.play();
}

function runAway() {
    let btn = document.getElementById("noBtn");

    // границы экрана
    let maxX = window.innerWidth - btn.offsetWidth - 20;
    let maxY = window.innerHeight - btn.offsetHeight - 20;

    // новая случайная позиция
    let newX = Math.random() * maxX;
    let newY = Math.random() * maxY;

    btn.style.left = newX + "px";
    btn.style.top = newY + "px";
}
</script>

</body>
</html>
