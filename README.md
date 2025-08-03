<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SAMPCinematicRP README</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            background-color: #f9f9f9;
        }
        h1, h2, h3 {
            color: #333;
        }
        h1 {
            border-bottom: 2px solid #007bff;
            padding-bottom: 10px;
        }
        h2 {
            margin-top: 20px;
        }
        pre, code {
            background-color: #f4f4f4;
            padding: 10px;
            border-radius: 5px;
            font-family: 'Courier New', Courier, monospace;
        }
        pre {
            overflow-x: auto;
        }
        ul {
            margin: 10px 0;
            padding-left: 20px;
        }
        a {
            color: #007bff;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
        .section {
            margin-bottom: 20px;
        }
        .code-block {
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <h1>SAMPCinematicRP</h1>
    <p>SAMPCinematicRP is a roleplay-focused gamemode script for San Andreas Multiplayer (SA-MP), a multiplayer mod for Grand Theft Auto: San Andreas. This project provides a modular, optimized, and cinematic roleplay experience with features like dynamic character creation, faction systems, and immersive storytelling elements. It’s designed for server owners and scripters who want to create a rich, narrative-driven multiplayer environment.</p>

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
        <p>SAMPCinematicRP is a PAWN-based gamemode for SA-MP servers, emphasizing roleplay with cinematic elements like scripted cutscenes, dynamic dialogues, and interactive environments. Key features include:</p>
        <ul>
            <li>MySQL database integration for persistent player and server data.</li>
            <li>Modular design with separate include files for systems like vehicles, factions, and jobs.</li>
            <li>Custom commands for roleplay interactions (e.g., <code>/me</code>, <code>/do</code>, <code>/changename</code>).</li>
            <li>Support for cinematic sequences using camera functions and text draws.</li>
            <li>Compatibility with SA-MP 0.3.7 and <a href="https://open.mp/">open.mp</a> (a backwards-compatible alternative).</li>
        </ul>
        <p>This script is ideal for creating immersive roleplay servers with a focus on storytelling and player interaction.</p>
    </div>

    <div class="section" id="technologies">
        <h2>Technologies</h2>
        <p>The project uses the following technologies:</p>
        <ul>
            <li><a href="https://wiki.sa-mp.com/wiki/PAWN">PAWN</a>: Scripting language for SA-MP.</li>
            <li><a href="https://www.mysql.com/">MySQL</a>: Version 5.7+ (via MySQL R41-4 plugin for data storage).</li>
            <li><a href="https://www.sa-mp.mp/">SA-MP</a>: Version 0.3.7 or later.</li>
            <li><a href="https://open.mp/">open.mp</a>: Optional, for enhanced server performance and features.</li>
            <li><a href="https://github.com/Southclaws/sampctl">sampctl</a>: For dependency management and build tools.</li>
            <li>Plugins: streamer, sscanf, mysql, crashdetect (included in <code>plugins/</code>).</li>
        </ul>
    </div>

    <div class="section" id="installation">
        <h2>Installation</h2>
        <p>Follow these steps to set up SAMPCinematicRP on your SA-MP server.</p>
        <h3>Prerequisites</h3>
        <ul>
            <li>SA-MP server package (download from <a href="https://www.sa-mp.mp/">sa-mp.mp</a> or <a href="https://open.mp/">open.mp</a>).</li>
            <li>MySQL server (local or hosted, version 5.7 or higher).</li>
            <li>Git (optional, for cloning the repository).</li>
            <li>sampctl (recommended, for dependency management).</li>
        </ul>
        <h3>Steps</h3>
        <div class="code-block">
            <pre><code># Clone the repository
$ git clone https://github.com/username/SAMPCinematicRP.git

# Navigate to the project directory
$ cd SAMPCinematicRP

# Install dependencies using sampctl (recommended)
$ sampctl package install

# Configure MySQL settings in `scriptfiles/config.ini`
# Example config.ini:
# [mysql]
# host = localhost
# user = root
# password = yourpassword
# database = sampcinematicrp

# Build the gamemode
$ sampctl package build

# Add the gamemode to server.cfg
# Example server.cfg:
# gamemode0 cinematicrp 1
# plugins streamer sscanf mysql crashdetect
</code></pre>
        </div>
        <p>Ensure the MySQL database is set up with the provided SQL schema in <code>scriptfiles/schema.sql</code>. Run the server executable (<code>samp-server.exe</code> or <code>openmp-server</code>) to start the server.</p>
    </div>

    <div class="section" id="usage">
        <h2>Usage</h2>
        <p>Once the server is running, players can connect using the SA-MP client. Below are some example commands for in-game roleplay and administration.</p>
        <h3>Player Commands</h3>
        <div class="code-block">
            <pre><code>/me [action] - Performs a roleplay action (e.g., /me waves at the crowd).
/do [description] - Describes an environmental or character action (e.g., /do The room is dimly lit).
/changename [newname] - Changes your character's roleplay name.
/spawncar [model] - Spawns a vehicle (restricted to admins).
</code></pre>
        </div>
        <h3>Admin Commands</h3>
        <div class="code-block">
            <pre><code>/setadmin [playerid] [level] - Sets a player's admin level (1-5).
/kick [playerid] [reason] - Kicks a player from the server.
/startcutscene [sceneid] - Triggers a predefined cinematic sequence.
</code></pre>
        </div>
        <h3>Example Script Output</h3>
        <p>An in-game interaction might look like this in the chat:</p>
        <div class="code-block">
            <pre><code>[RP] John_Doe: *waves at the crowd*
[RP] John_Doe: /do The crowd cheers loudly.
John_Doe: Let's make this a night to remember!
</code></pre>
        </div>
        <p>Check the <code>examples/</code> folder for sample cutscene scripts and faction configurations.</p>
    </div>

    <div class="section" id="script-structure">
        <h2>Script Structure</h2>
        <p>The gamemode is organized into modular include files for easy maintenance:</p>
        <ul>
            <li><code>gamemodes/cinematicrp.pwn</code>: Main gamemode file.</li>
            <li><code>includes/player.inc</code>: Player registration, login, and character systems.</li>
            <li><code>includes/factions.inc</code>: Faction creation and management.</li>
            <li><code>includes/vehicles.inc</code>: Vehicle spawning and customization.</li>
            <li><code>includes/cutscenes.inc</code>: Cinematic camera and text draw functions.</li>
            <li><code>scriptfiles/config.ini</code>: Server configuration (MySQL, settings).</li>
        </ul>
        <p>Key PAWN functions used include <code>TextDrawShowForPlayer</code>, <code>SetPlayerCameraPos</code>, and <code>mysql_tquery</code> for database interactions. Refer to the <a href="https://wiki.sa-mp.com/">SA-MP Wiki</a> for detailed function documentation.</p>
    </div>

    <div class="section" id="contributing">
        <h2>Contributing</h2>
        <p>We welcome contributions! To contribute:</p>
        <ol>
            <li>Fork the repository.</li>
            <li>Create a new branch (<code>git checkout -b feature-branch</code>).</li>
            <li>Make your changes and commit (<code>git commit -m "Add new feature"</code>).</li>
            <li>Push to your branch (<code>git push origin feature-branch</code>).</li>
            <li>Open a pull request on GitHub.</li>
        </ol>
        <p>Please follow the coding style in existing files and test your changes locally. See <code>CONTRIBUTING.md</code> for detailed guidelines.</p>
    </div>

    <div class="section" id="license">
        <h2>License</h2>
        <p>This project is licensed under the MIT License. See the <code>LICENSE</code> file for details.</p>
    </div>

    <div class="section" id="contact">
        <h2>Contact</h2>
        <p>For questions or collaboration, reach out via:</p>
        <ul>
            <li>Email: <a href="mailto:your.email@example.com">your.email@example.com</a></li>
            <li>GitHub Issues: <a href="https://github.com/username/SAMPCinematicRP/issues">SAMPCinematicRP Issues</a></li>
            <li>X: <a href="https://x.com/YourHandle">@YourHandle</a></li>
        </ul>
    </div>
</body>
</html>
