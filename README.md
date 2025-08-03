SAMPCinematicRP
SAMPCinematicRP is a roleplay-focused gamemode script for San Andreas Multiplayer (SA-MP), a multiplayer mod for Grand Theft Auto: San Andreas. This project offers a modular, optimized, and cinematic roleplay experience with dynamic character creation, faction systems, and immersive storytelling elements. It’s designed for server owners and scripters aiming to create a narrative-driven multiplayer environment.
Table of Contents

General Info
Technologies
Installation
Usage
Script Structure
Contributing
License
Contact

General Info
SAMPCinematicRP is a PAWN-based gamemode for SA-MP servers, emphasizing roleplay with cinematic features like scripted cutscenes, dynamic dialogues, and interactive environments. Key features include:

MySQL integration for persistent player and server data.
Modular design with separate includes for vehicles, factions, and jobs.
Roleplay commands (e.g., /me, /do, /changename).
Cinematic sequences using camera functions and text draws.
Compatibility with SA-MP 0.3.7 and open.mp.

This script is perfect for creating immersive roleplay servers with a focus on storytelling.
Technologies
The project uses the following technologies:

PAWN: SA-MP scripting language.
MySQL: Version 5.7+ (via MySQL R41-4 plugin).
SA-MP: Version 0.3.7 or later.
open.mp: Optional, for enhanced performance.
sampctl: Dependency management.
Plugins: streamer, sscanf, mysql, crashdetect.

Installation
Follow these steps to set up SAMPCinematicRP on your SA-MP server.
Prerequisites

SA-MP server package (sa-mp.mp or open.mp).
MySQL server (version 5.7+).
Git (optional).
sampctl (recommended).

Steps
# Clone the repository
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

Import the SQL schema from scriptfiles/schema.sql into your MySQL database. Start the server using samp-server.exe or openmp-server.
Usage
Players can connect via the SA-MP client. Below are example commands for roleplay and administration.
Player Commands
/me [action] - Performs an action (e.g., /me waves at the crowd).
/do [description] - Describes an environment (e.g., /do The room is dimly lit).
/changename [newname] - Changes your roleplay name.
/spawncar [model] - Spawns a vehicle (admin-only).

Admin Commands
/setadmin [playerid] [level] - Sets admin level (1-5).
/kick [playerid] [reason] - Kicks a player.
/startcutscene [sceneid] - Triggers a cinematic sequence.

Example Output
[RP] John_Doe: *waves at the crowd*
[RP] John_Doe: /do The crowd cheers loudly.
John_Doe: Let's make this a night to remember!

See the examples/ folder for sample cutscenes and configurations.
Script Structure
The gamemode is modular for easy maintenance:

gamemodes/cinematicrp.pwn: Main gamemode file.
includes/player.inc: Player systems (registration, login).
includes/factions.inc: Faction management.
includes/vehicles.inc: Vehicle systems.
includes/cutscenes.inc: Cinematic functions.
scriptfiles/config.ini: Server configuration.

Uses PAWN functions like TextDrawShowForPlayer, SetPlayerCameraPos, and mysql_tquery. See the SA-MP Wiki for details.
Contributing
To contribute:

Fork the repository.
Create a branch (git checkout -b feature-branch).
Commit changes (git commit -m "Add feature").
Push to your branch (git push origin feature-branch).
Open a pull request.

Follow the coding style and test changes locally. See CONTRIBUTING.md for guidelines.
License
Licensed under the MIT License. See LICENSE for details.
Contact

Email: your.email@example.com
GitHub Issues: SAMPCinematicRP Issues
X: @YourHandle
