<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cinematic SA-MP RPG – README</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #0f0f0f;
      color: #f5f5f5;
      padding: 30px;
      line-height: 1.6;
    }
    h1, h2 {
      color: #ffd700;
    }
    .section {
      margin-bottom: 40px;
    }
    .feature {
      background: #1a1a1a;
      padding: 15px;
      border-left: 4px solid #ffcc00;
      margin-bottom: 10px;
      border-radius: 5px;
    }
    code {
      background: #333;
      padding: 4px 8px;
      border-radius: 4px;
      color: #00ffcc;
    }
    .btn {
      background: #ffcc00;
      color: #000;
      padding: 10px 20px;
      text-decoration: none;
      border-radius: 6px;
      font-weight: bold;
    }
    .btn:hover {
      background: #ffaa00;
    }
    .footer {
      margin-top: 50px;
      font-size: 14px;
      color: #888;
    }
  </style>
</head>
<body>

  <h1>🎬 Cinematic SA-MP RPG – Dynamic Movie Server</h1>
  <p>Bring Hollywood to San Andreas with a full-featured dynamic RPG script designed for cinematic storytelling, immersive missions, and RPG-driven character development.</p>

  <div class="section">
    <h2>🚀 Features</h2>
    <div class="feature">🎥 <strong>Dynamic Movie System</strong> – Create and direct scenes with camera angles, fades, props, and actors.</div>
    <div class="feature">🎭 <strong>RPG Character Classes</strong> – Become an Actor, Director, Cameraman, Editor, or even a Stuntman.</div>
    <div class="feature">🏗️ <strong>Scene Builder</strong> – Setup in-game sets using a map editor interface and custom object spawns.</div>
    <div class="feature">🎶 <strong>Soundtrack Support</strong> – Integrate music into scenes via dialog selections or preloaded sound IDs.</div>
    <div class="feature">📽️ <strong>Scene Playback</strong> – Replay recorded scenes with actors' positions, animations, and dialogues.</div>
    <div class="feature">💬 <strong>Cinematic Dialog System</strong> – Add immersive in-scene dialogues with timing and emotion triggers.</div>
    <div class="feature">🎞️ <strong>Dynamic Role Assigning</strong> – Assign roles to players in real-time, handle auditions, and scene rehearsal.</div>
    <div class="feature">🧠 <strong>MySQL + SQLite Support</strong> – All progress, scripts, and player data are saved securely.</div>
  </div>

  <div class="section">
    <h2>🔧 Installation</h2>
    <ol>
      <li>Clone the repository:
        <pre><code>git clone https://github.com/youruser/cinematic-samp-rpg.git</code></pre>
      </li>
      <li>Import the SQL file to your MySQL server.</li>
      <li>Edit your `server.cfg`:
        <pre><code>gamemode0 cinematic 1<br>plugins mysql sscanf streamer</code></pre>
      </li>
      <li>Compile the script using Pawn Compiler.</li>
      <li>Run your server and start directing!</li>
    </ol>
  </div>

  <div class="section">
    <h2>📸 Example Commands</h2>
    <pre>
/scene create <scene_name>
/scene addactor <playerid>
/scene adddialog <text>
/scene play
/movie start
/job director
    </pre>
  </div>

  <div class="section">
    <h2>📂 Folder Structure</h2>
    <pre>
/gamemodes
  cinematic.pwn
/scriptfiles
  scenes/
  actors/
  settings.ini
/plugins
  mysql.dll
  streamer.dll
    </pre>
  </div>

  <div class="section">
    <a href="https://github.com/youruser/cinematic-samp-rpg" class="btn">⭐ Star on GitHub</a>
  </div>

  <div class="footer">
    Made with 🎬 and 🧠 by <strong>Night Knight263 & Team</strong> | Powered by SA-MP
  </div>

</body>
</html>
