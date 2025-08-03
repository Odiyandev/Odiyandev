<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SAMPCinematicRP README</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        h1, h2, h3 {
            color: #24292e;
        }
        h1 {
            border-bottom: 1px solid #eaecef;
            padding-bottom: 10px;
        }
        pre, code {
            background-color: #f6f8fa;
            border-radius: 6px;
            padding: 10px;
            font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, Courier, monospace;
            font-size: 85%;
        }
        pre {
            overflow-x: auto;
        }
        a {
            color: #0366d6;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
        ul {
            padding-left: 20px;
        }
        .section {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <h1>SAMPCinematicRP</h1>
    <p>SAMPCinematicRP is a roleplay-focused gamemode script for <a href="https://www.sa-mp.mp/">San Andreas Multiplayer (SA-MP)</a>, a multiplayer mod for Grand Theft Auto: San Andreas. This project offers a modular, optimized, and cinematic roleplay experience with dynamic character creation, faction systems, and immersive storytelling elements. It’s designed for server owners and scripters aiming to create a narrative-driven multiplayer environment.</p>

    <div class="section">
        <h2>Table of Contents</h2>
        <ul>
            <li><a href="#general-info">General Info</a></li>
            <li><a href="#technologies">Technologies</a></li>
            <li><a href="#installation">Installation</a></li>
            <li><a href="#usage">Usage</a></li>
            <li><a href="#script-structure">Script Structure</a></li>
            <li><a href="#contributing">Contributing</a></li>
            <li><a href="#license">License</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </div>

    <div class="section" id="general-info">
        <h2>General Info</h2>
        <p>SAMPCinematicRP is a PAWN-based gamemode for SA-MP servers, emphasizing roleplay with cinematic features like scripted cutscenes, dynamic dialogues, and interactive environments. Key features include:</p>
        <ul>
            <li>MySQL integration for persistent player and server data.</li>
            <li>Modular design with separate includes for vehicles, factions, and jobs.</li>
            <li>Roleplay commands (e.g., <code>/me</code>, <code>/do</code>, <code>/changename</code>).</li>
            <li>Cinematic sequences using camera functions and text draws.</li>
            <li>Compatibility with SA-MP 0.3.7 and <a href="https://open.mp/">open.mp</a>.</li>
        </ul>
        <p>This script is perfect for creating immersive roleplay servers with a focus on storytelling.</p>
    </div>

    <div class="section" id="technologies">
        <h2>Technologies</h2>
        <p>The project uses the following technologies:</p>
        <ul>
            <li><a href="https://wiki.sa-mp.com/wiki/PAWN">PAWN</a>: SA-MP scripting language.</li>
            <li><a href="https://www.mysql.com/">MySQL</a>: Version 5.7+ (via MySQL R41-4 plugin).</li>
            <li><a href="https://www.sa-mp.mp/">SA-MP</a>: Version 0.3.7 or later.</li>
            <li><a href="https://open.mp/">open.mp</a>: Optional, for enhanced performance.</li>
            <li><a href="https://github.com/Southclaws/sampctl">sampctl</a>: Dependency management.</li>
            <li>Plugins: streamer, sscanf, mysql, crashdetect.</li>
        </ul>
    </div>

    <div class="section" id="installation">
        <h2>Installation</h2>
        <p>Follow these steps to set up SAMPCinematicRP on your SA-MP server.</p>
        <h3>Prerequisites</h3>
        <ul>
            <li>SA-MP server package (<a href="https://www.sa-mp.mp/">sa-mp.mp</a> or <a href="https://open.mp/">open.mp</a>).</li>
            <li>MySQL server (version 5.7+).</li>
            <li>Git (optional).</li>
            <li>sampctl (recommended).</li>
        </ul>
        <h3>Steps</h3>
        <pre><code># Clone the repository
$ git clone https://github.com/username/SAMPCinematicRP.git

# Navigate to the project directory
$ cd SAMPCinematicRP

# Install dependencies using sampctl
$ sampctl package install

# Configure MySQL in `scriptfiles/config.ini`
# Example:
# [mysql]
# host = localhost
# user = root
# password = yourpassword
# database = sampcinematicrp

# Build the gamemode
$ sampctl package build

# Update server.cfg
# Example:
# gamemode0 cinematicrp 1
# plugins streamer sscanf mysql crashdetect
</code></pre>
        <p>Import the SQL schema from <code>scriptfiles/schema.sql</code> into your MySQL database. Start the server using <code>samp-server.exe</code> or <code>openmp-server</code>.</p>
    </div>

    <div class="section" id="usage">
        <h2>Usage</h2>
        <p>Players can connect via the SA-MP client. Below are example commands for roleplay and administration.</p>
        <h3>Player Commands</h3>
        <pre><code>/me [action] - Performs an action (e.g., /me waves at the crowd).
/do [description] - Describes an environment (e.g., /do The room is dimly lit).
/changename [newname] - Changes your roleplay name.
/spawncar [model] - Spawns a vehicle (admin-only).
</code></pre>
        <h3>Admin Commands</h3>
        <pre><code>/setadmin [playerid] [level] - Sets admin level (1-5).
/kick [playerid] [reason] - Kicks a player.
/startcutscene [sceneid] - Triggers a cinematic sequence.
</code></pre>
        <h3>Example Output</h3>
        <pre><code>[RP] John_Doe: *waves at the crowd*
[RP] John_Doe: /do The crowd cheers loudly.
John_Doe: Let's make this a night to remember!
</code></pre>
        <p>See the <code>examples/</code> folder for sample cutscenes and configurations.</p>
    </div>

    <div class="section" id="script-structure">
        <h2>Script Structure</h2>
        <p>The gamemode is modular for easy maintenance:</p>
        <ul>
            <li><code>gamemodes/cinematicrp.pwn</code>: Main gamemode file.</li>
            <li><code>includes/player.inc</code>: Player systems (registration, login).</li>
            <li><code>includes/factions.inc</code>: Faction management.</li>
            <li><code>includes/vehicles.inc</code>: Vehicle systems.</li>
            <li><code>includes/cutscenes.inc</code>: Cinematic functions.</li>
            <li><code>scriptfiles/config.ini</code>: Server configuration.</li>
        </ul>
        <p>Uses PAWN functions like <code>TextDrawShowForPlayer</code>, <code>SetPlayerCameraPos</code>, and <code>mysql_tquery</code>. See the <a href="https://wiki.sa-mp.com/">SA-MP Wiki</a> for details.</p>
    </div>

    <div class="section" id="contributing">
        <h2>Contributing</h2>
        <p>To contribute:</p>
        <ol>
            <li>Fork the repository.</li>
            <li>Create a branch (<code>git checkout -b feature-branch</code>).</li>
            <li>Commit changes (<code>git commit -m "Add feature"</code>).</li>
            <li>Push to your branch (<code>git push origin feature-branch</code>).</li>
            <li>Open a pull request.</li>
        </ol>
        <p>Follow the coding style and test changes locally. See <code>CONTRIBUTING.md</code> for guidelines.</p>
    </div>

    <div class="section" id="license">
        <h2>License</h2>
        <p>Licensed under the MIT License. See <code>LICENSE</code> for details.</p>
    </div>

    <div class="section" id="contact">
        <h2>Contact</h2>
        <ul>
            <li>Email: <a href="mailto:your.email@example.com">your.email@example.com</a></li>
            <li>GitHub Issues: <a href="https://github.com/username/SAMPCinematicRP/issues">Issues</a></li>
            <li>X: <a href="https://x.com/YourHandle">@YourHandle</a></li>
        </ul>
    </div>
</body>
</html>
