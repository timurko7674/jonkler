<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jonkler</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #000;
            color: #fff;
            flex-direction: column;
            font-family: Arial, sans-serif;
            user-select: none; /* Prevents text selection */
        }
        img {
            max-width: 100%;
            max-height: 80%;
        }
    </style>
</head>
<body>
    <img src="jonkler.png" alt="Jonkler">
    <audio id="sound" src="jonkler.mp3" loop></audio>

    <script>
        const audio = document.getElementById('sound');
        let audioPlayed = false; // To ensure it plays only once on interaction

        // Play the audio on any keyboard or mouse interaction
        function startAudio() {
            if (!audioPlayed) {
                audio.play().then(() => {
                    console.log("Audio started playing!");
                    audioPlayed = true; // Prevent further triggers
                }).catch(error => {
                    console.error("Audio playback failed:", error);
                });
            }
        }

        // Add event listeners for keyboard and mouse
        document.addEventListener('keydown', startAudio);
        document.addEventListener('click', startAudio);
    </script>
</body>
</html>
