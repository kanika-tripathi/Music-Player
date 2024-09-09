# Music-Player
This is a simple music player program created using HTML, CSS and JavaScript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Music Player</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }
        .player {
            text-align: center;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .controls {
            margin-top: 10px;
        }
        button {
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
            font-size: 14px;
        }
        button:hover {
            background-color: #0056b3;
        }
        button:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }
    </style>
</head>
<body>
    <div class="player">
        <h1>Music Player</h1>
        <audio id="audio" controls>
            <source src="your-audio-file.mp3" type="audio/mp3">
            Your browser does not support the audio element.
        </audio>
        <div class="controls">
            <button id="playPauseBtn">Play</button>
            <button id="stopBtn">Stop</button>
            <button id="muteBtn">Mute</button>
            <button id="volumeUpBtn">Volume Up</button>
            <button id="volumeDownBtn">Volume Down</button>
        </div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const audio = document.getElementById('audio');
            const playPauseBtn = document.getElementById('playPauseBtn');
            const stopBtn = document.getElementById('stopBtn');
            const muteBtn = document.getElementById('muteBtn');
            const volumeUpBtn = document.getElementById('volumeUpBtn');
            const volumeDownBtn = document.getElementById('volumeDownBtn');
                        playPauseBtn.addEventListener('click', () => {
                if (audio.paused) {
                    audio.play();
                    playPauseBtn.textContent = 'Pause';
                } else {
                    audio.pause();
                    playPauseBtn.textContent = 'Play';
                }
            });
            stopBtn.addEventListener('click', () => {
                audio.pause();
                audio.currentTime = 0;
                playPauseBtn.textContent = 'Play';
            });
            muteBtn.addEventListener('click', () => {
                audio.muted = !audio.muted;
                muteBtn.textContent = audio.muted ? 'Unmute' : 'Mute';
            });
            volumeUpBtn.addEventListener('click', () => {
                if (audio.volume < 1) audio.volume += 0.1;
            });
            volumeDownBtn.addEventListener('click', () => {
                if (audio.volume > 0) audio.volume -= 0.1;
            });
        });
    </script>
</body>
</html>
