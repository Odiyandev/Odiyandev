<!DOCTYPE html>
<html>
<head>
  <title>Cinematic SA-MP RPG Script - README</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #111; color: #eee; padding: 20px;">

  <h1 style="color: gold;">🎬 Cinematic SA-MP RPG – Script ReadMe</h1>
  <p>A feature-packed SA-MP gamemode for dynamic movie creation, acting jobs, RPG leveling, and cinematic experiences.</p>

  <h2 style="color: orange;">🚀 Features</h2>
  <ul>
    <li>Dynamic Scene & Movie Creation</li>
    <li>Actor/Director/Cameraman RPG Roles</li>
    <li>Cinematic Camera, Animations, and Dialogues</li>
    <li>Custom Sets, Props & Scene Replays</li>
    <li>Soundtrack Integration</li>
    <li>MySQL-based persistent data system</li>
  </ul>

  <h2 style="color: orange;">💻 Localhost Installation</h2>
  <ol>
    <li>Download and install <b>XAMPP</b> or <b>WAMP</b> (for MySQL & PHPMyAdmin).</li>
    <li>Start <b>Apache</b> and <b>MySQL</b> services.</li>
    <li>Open <b>http://localhost/phpmyadmin</b></li>
    <li>Create a new database, e.g., <code>cinematic_rpg</code></li>
    <li>Import the provided <code>cinematic_rpg.sql</code> file into your database.</li>
    <li>Open your SA-MP server folder and edit <code>server.cfg</code>:
      <pre>
plugins mysql sscanf streamer
gamemode0 cinematic 1
      </pre>
    </li>
    <li>Edit your script’s <code>mysql_connect</code> code:
      <pre>
mysql_connect("localhost", "root", "", "cinematic_rpg");
      </pre>
    </li>
    <li>Compile the script using <b>pawno</b> or <b>sampctl</b>.</li>
    <li>Run <code>samp-server.exe</code> and join via <code>127.0.0.1:7777</code> in SA-MP.</li>
  </ol>

  <h2 style="color: orange;">📜 Sample Commands</h2>
  <ul>
    <li><code>/scene create [name]</code> - Create new movie scene</li>
    <li><code>/actor join</code> - Become an actor</li>
    <li><code>/director tools</code> - Access camera and set tools</li>
    <li><code>/scene play</code> - Start scene recording/playback</li>
    <li><code>/job list</code> - View all cinematic jobs</li>
  </ul>

  <h2 style="color: orange;">📂 Script Structure</h2>
  <ul>
    <li><b>/gamemodes/cinematic.pwn</b> - Main game logic</li>
    <li><b>/scriptfiles/scenes/</b> - Scene storage</li>
    <li><b>/scriptfiles/settings.ini</b> - Configs</li>
    <li><b>/plugins/</b> - mysql, streamer, sscanf</li>
  </ul>

  <h2 style="color: orange;">📣 Notes</h2>
  <ul>
    <li>Default DB login: user = <code>root</code>, password = <code>(empty)</code></li>
    <li>If using WAMP/XAMPP, make sure port 3306 is open for MySQL.</li>
    <li>Don't forget to load plugins before script runs.</li>
  </ul>

  <hr>
  <p>Made with ❤️ by <b>Night Knight263</b> | For SA-MP Community</p>

</body>
</html>
