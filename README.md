# Music-player-using-JavaScript-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Music Player</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: #181818;
      color: white;
      font-family: Arial, sans-serif;
    }

    .player {
      background: #282828;
      padding: 30px;
      border-radius: 12px;
      text-align: center;
      width: 300px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.3);
    }

    .song-info {
      margin-bottom: 20px;
    }

    .song-title {
      font-size: 20px;
      font-weight: bold;
    }

    .song-artist {
      font-size: 14px;
      color: #bbb;
    }

    .controls {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    button {
      background: #1db954;
      border: none;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      color: white;
      font-size: 20px;
      cursor: pointer;
      transition: background 0.2s;
    }

    button:hover {
      background: #1ed760;
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>
  <div class="player">
    <div class="song-info">
      <div class="song-title" id="title">Sample Song</div>
      <div class="song-artist" id="artist">Unknown Artist</div>
    </div>
    <div class="controls">
      <button onclick="playPause()">▶</button>
      <button onclick="stopSong()">■</button>
    </div>
    <audio id="audio" src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"></audio>
  </div>

  <script>
    const audio = document.getElementById("audio");
    let isPlaying = false;

    function playPause() {
      if (isPlaying) {
        audio.pause();
      } else {
        audio.play();
      }
      isPlaying = !isPlaying;
    }

    function stopSong() {
      audio.pause();
      audio.currentTime = 0;
      isPlaying = false;
    }
  </script>
</body>
</html>
