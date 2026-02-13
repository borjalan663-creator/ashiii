# ashiii
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ashi 💖</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Comic Sans MS', cursive, sans-serif;
    }

    body {
        height: 100vh;
        background: linear-gradient(135deg, #a3d9ff, #d0f0ff);
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        overflow: hidden;
        text-align: center;
    }

    h1 {
        font-size: 2.8rem;
        color: #007acc;
        margin-bottom: 20px;
    }

    button {
        padding: 12px 28px;
        font-size: 1.2rem;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        margin: 10px;
        transition: 0.3s;
    }

    #yesBtn {
        background: #00bfff;
        color: white;
    }

    #yesBtn:hover {
        transform: scale(1.1);
    }

    #noBtn {
        background: #cccccc;
        position: absolute;
    }

    .hidden {
        display: none;
    }

    .success {
        font-size: 2.5rem;
        color: #0099ff;
        animation: pop 0.6s ease forwards;
    }

    @keyframes pop {
        0% { transform: scale(0.5); opacity: 0; }
        100% { transform: scale(1); opacity: 1; }
    }

    .heart {
        position: absolute;
        font-size: 24px;
        animation: float 4s linear infinite;
        color: #00bfff;
    }

    @keyframes float {
        0% { transform: translateY(100vh) scale(1); opacity: 1; }
        100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
    }

    .gif {
        width: 220px;
        margin-top: 20px;
        border-radius: 20px;
    }
</style>
</head>

<body>

<h1 id="question">Will you be my Valentine? 💖</h1>

<div id="buttons">
    <button id="yesBtn">Yes 💕</button>
    <button id="noBtn">No 😢</button>
</div>

<img id="cuteGif" class="gif"
src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif"
alt="cute">

<h1 id="successMessage" class="hidden success">
    Yayyy thankk youu ashi mwehehehehe 💕
</h1>

<img id="celebrateGif" class="gif hidden"
src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif"
alt="celebrate">

<!-- Embedded YouTube Song -->
<iframe id="musicPlayer" class="hidden"
    width="0" height="0"
    src="https://www.youtube.com/embed/6DcUnqZqTvI?autoplay=1&loop=1&playlist=6DcUnqZqTvI"
    allow="autoplay"
></iframe>

<script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const question = document.getElementById("question");
    const buttons = document.getElementById("buttons");
    const successMessage = document.getElementById("successMessage");
    const cuteGif = document.getElementById("cuteGif");
    const celebrateGif = document.getElementById("celebrateGif");
    const musicPlayer = document.getElementById("musicPlayer");

    yesBtn.addEventListener("click", () => {
        question.classList.add("hidden");
        buttons.classList.add("hidden");
        cuteGif.classList.add("hidden");
        successMessage.classList.remove("hidden");
        celebrateGif.classList.remove("hidden");
        musicPlayer.classList.remove("hidden"); // Start the song
        startHearts();
    });

    noBtn.addEventListener("mouseover", () => {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = `${x}px`;
        noBtn.style.top = `${y}px`;
    });

    function startHearts() {
        setInterval(() => {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "💖";
            heart.style.left = Math.random() * window.innerWidth + "px";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 4000);
        }, 300);
    }
</script>

</body>
</html>
