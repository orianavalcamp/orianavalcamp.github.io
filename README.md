<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Oriana Valcamp Assignment #1</title>
    
    <style>
    body {
        background-color: darkgrey;
        font-family: courier;
    }

    .container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }

    .item {
        width: 100%;
        max-width: 400px;
        margin: 20px;
        text-align: center;
    }

    img {
        width: 100%;
        height: auto;
    }

    .button {
        font-family: courier;
        font-size: 1.5rem;
        border: none;
        width: auto;
        cursor: pointer;
    }

    .button1 {
        background-color: lightblue;
        color: darkblue;
    }

    .button1:hover,
    .button1:focus {
        background-color: darkblue;
        color: lightblue;
    }

    .button2 {
        background-color: orange;
        color: orangered;
    }

    .button2:hover,
    .button2:focus {
        background-color: orangered;
        color: orange;
    }

    .button3 {
        background-color: tan;
        color: saddlebrown;
    }

    .button3:hover,
    .button3:focus {
        background-color: saddlebrown;
        color: tan;
    }

</style>

</head>
<body>
    <div style="text-align: center; font-family: courier" >
        <h1>Audio Website</h1>
    </div>

    <audio id="audioPlayer1" src="johnsummit.mp3" type="audio/mpeg"></audio>
    <audio id="audioPlayer2" src="hozier.mp3" type="audio/mpeg"></audio>
    <audio id="audioPlayer3" src="noahkahan.mp3" type="audio/mpeg"></audio>

    <div class="container">
        <div class="item">
            <img src="hozier.jpeg" alt="Album Art">
            <div>
                <br>

                <button class="button button2" onclick="playAudio2()">Play</button>
                <button class="button button2" onclick="pauseAudio2()">Pause</button>

                <br>
                <br>

                <button class="button button2" onclick="setPlaybackRate2(0.5)">0.5x</button>
                <button class="button button2" onclick="setPlaybackRate2(1)">1x</button>
                <button class="button button2" onclick="setPlaybackRate2(2)">2x</button>
            </div>
        </div>

        <div class="item">
            <img src="johnsummit.jpeg" alt="Album Art">
            <div>
                <br>

                <button class="button button1" onclick="playAudio1()">Play</button>
                <button class="button button1" onclick="pauseAudio1()">Pause</button>

                <br>
                <br>

                <button class="button button1" onclick="setPlaybackRate1(0.5)">0.5x</button>
                <button class="button button1" onclick="setPlaybackRate1(1)">1x</button>
                <button class="button button1" onclick="setPlaybackRate1(2)">2x</button>
            </div>
        </div>

        <div class="item">
            <img src="noahkahan.jpeg" alt="Album Art">
            <div>
                <br>

                <button class="button button3" onclick="playAudio3()">Play</button>
                <button class="button button3" onclick="pauseAudio3()">Pause</button>

                <br>
                <br>
                
                <button class="button button3" onclick="setPlaybackRate3(0.5)">0.5x</button>
                <button class="button button3" onclick="setPlaybackRate3(1)">1x</button>
                <button class="button button3" onclick="setPlaybackRate3(2)">2x</button>
            </div>
        </div>
    </div>

    <script>
        const audio = document.getElementById('audioPlayer1');
        const audio2 = document.getElementById('audioPlayer2');
        const audio3 = document.getElementById('audioPlayer3');

        let currentAudio = null; // Variable to track currently playing audio

        function playAudio1() {
            playAudio(audio);
        }

        function playAudio2() {
            playAudio(audio2);
        }

        function playAudio3() {
            playAudio(audio3);
        }

        function playAudio(audioElement) {
        // Stop currently playing audio if there's one
            if (currentAudio && currentAudio !== audioElement) {
                currentAudio.pause();
                currentAudio.currentTime = 0; // Reset the time to the start
            }
            audioElement.play();
            currentAudio = audioElement; // Set the currently playing audio
        }

    function pauseAudio1() {
        pauseAudio(audio);
    }

    function pauseAudio2() {
        pauseAudio(audio2);
    }

    function pauseAudio3() {
        pauseAudio(audio3);
    }

    function pauseAudio(audioElement) {
        audioElement.pause();
        if (currentAudio === audioElement) {
            currentAudio = null; // Reset if the paused audio was the current one
        }
    }

    function setPlaybackRate1(rate) {
        setPlaybackRate(audio, rate);
    }

    function setPlaybackRate2(rate) {
        setPlaybackRate(audio2, rate);
    }

    function setPlaybackRate3(rate) {
        setPlaybackRate(audio3, rate);
    }

    function setPlaybackRate(audioElement, rate) {
        audioElement.playbackRate = rate;
    }
</script>
</body>
</html>
