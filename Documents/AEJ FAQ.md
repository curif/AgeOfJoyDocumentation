# AGE of Joy 
## What is AGE of Joy?
AGE of Joy (`AGE` in short) is an experience/game/simulation. This experience is an attempt to preserve the arcade galleries of the old days, that feeling, in a virtual world where anyone with a VR headset can experiment with it.

## Ok, I want to download it.
Go [here](https://curifab.itch.io/age-of-joy).
## Can I play it on a PC?
No, only plays in Meta Quest 2 (at the moment when this document was written).
## How much it cost?
You can make a donation to the developer, but it is not strictly necessary. Download and enjoy it.
## How to install AGE? 
* Download from this [itchio page](https://curifab.itch.io/age-of-joy) (you can download release candidates from GitHub too, but they are not stable).
* Backup the previous version (from the Quest to your PC) if you already install it.
* Install the game using [Sidequest](https://sidequestvr.com/) (follow [[Sidequest]] instructions to install it): [Instructions](https://learn.adafruit.com/sideloading-on-oculus-quest/install-and-use-sidequest)
Note that you need to enable the developer mode to sideload programs. It's the way that developers run applications: [Enable developer mode](https://learn.adafruit.com/sideloading-on-oculus-quest/enable-developer-mode)
## I install it but I only see black ugly cabinets! what is wrong?
Nothing, that's how AGE should look when you install it. It is necessary to upload cabinets to deploy in the rooms. And you also need ROMs if you want to play.
## I have problems when play, what can I do?
AGE is in active development and has not been fully achieved. Errors and problems will surely arise.
Read the documentation first, and ask in Discord later if you can't resolve your issues. 
## Can I configure the game, like to quit the NPCs or the sound?
Yes you can do it by changing the game configuration files, read how to do it here: [[AGE configuration using files]]
## Can I configure the game being in the game? I don't like to change files.
At the moment it is the only way. In the future there will be configuration screens in the game.


# ROMS
## What is a rom?
A [[ROM]] is a file that represents a retro game (non techie response). Usually they have a filename ending with `.zip` like `galaga.zip`.

You need a [[ROM]] and an emulator like MAME to play old games.
## What is MAME?
[MAME](https://www.mamedev.org/) is the arcade machine emulator.
## What is an emulator?
An emulator is a software that emulates another software or hardware. In our case MAME emulate old arcade machines.
## Can I play AGE of Joy without ROMs?
You can get into the game and relive the experience of being in an arcade, but you can't play any arcade game without ROMs. In that case you can put the coin but nothing happens
## Why AGE of Joy don't have ROMS in the game?
It's illegal to distribute any copyrighted material without permission.
## It is legal to possess a ROM?
ROMs are copyrighted material, so be careful to not violate the intellectual property. 
## Where can I find them?
On internet. You can make a simply search like [MAME 2003-Plus Reference: Full Non-Merged Romsets](https://www.google.com/search?q=MAME+2003-Plus+Reference%3A+Full+Non-Merged+Romsets&sourceid=chrome&ie=UTF-8)
## I have a ROM, can I play it in AGE of Joy?
Not all ROMs are available to play, inconsistencies, bugs and incompatibilities exists. Usually if you can find a cabinet for a game then the [[ROM]] exists and is playable.
## I need a cabinet file to play with a ROM?
Yes, you need it, as in the old days, each cabinet had mainly one set. Read the cabinet section in this document. 
## MD5 checksum
### What is a md5 checksum/token?
The md5 is a token that is useful to validate if your [[ROM]] is the correct. An md5 looks like `56a6c44c2d6678bdc085b8780bc51819`
### How can I check if my [[ROM]] is the correct using an MD5?
First you need the md5 of the tested rom, you can get it in the `description.yaml` file inside the cabinet file. Or you can get it by looking the page of each game in this site. Then compare it with the md5 of your own ROM, you can get your md5 here: [MD5 Hash Calculator](https://curif.github.io/AgeOfJoy-ROMCRC/index.html). Compare both md5, if they are exactly the same then you have the correct ROM.
## Where to upload the ROM?
Copy the [[ROM]] to `/sdcard/Android/data/com.curif.AgeOfJoy/downloads` using [[Sidequest]].
## So I have to decompress the zip file, right?
NO, just copy the zip file to the folder.
## I can't find the folder!
You must run AGE at least once to create the folders.


# Playing games
## How can I play an emulated game?
If you have a cabinet and a [[ROM]] you can play the game. Just put a coin on it: [video](https://youtu.be/MYOKp9lI_7o).

Also read the [controller documentation](https://curifab.itch.io/age-of-joy/devlog/457164/age-of-joy-quest-2-controls).
## I'm playing now, how to leave?
Press the grip button in your left control for some seconds.
## Can I insert a coin when I'm playing?
Yes you can do it.
## Can I change the buttons distribution and actions?
Yes you can, but you have to know that this is a MAME function, not is something related with AGE. To control the MAME emulation press the trigger and the joystick at same time in your right control when you are in game mode, a menu appears inside the game.
## I want to play sited, can I?
Yes, you need to configure the Quest Accessibility Options. By doing so, you will see the world of virtual reality as if you were standing upright.

# Cabinets
## What is a cabinet?
Old games comes in its own cabinets. So to play a game you need to download a cabinet and upload it to your Quest.
## Where can I download cabinets?
You need to "hunt" them on internet. The best place to start is this site.
There a lot of cabinets made by the community, get those in [Discord](https://discord.gg/b83ykCM9Xp)
## how to instal cabinets in AGE?
Read  [[How to get and deploy cabinets assets]]
## I have a cabinet file, how to upload it?
Copy the zip file to `/sdcard/Android/data/com.curif.AgeOfJoy/cabinets`
## So I have to decompress the zip file, right?
NO, just copy the zip file to the folder.
## I can't find the folder!
You must run AGE at least once to create the folders
## I'm confused, the cabinet file and the [[ROM]] file have the same name...
Yes, it is not strictly necessary but it is a convention. We can know that the cabinet is for a certain game that way.
## I want to make my own cabinets, can I?
Yes you can, but first check it if someone didn't made it. Then you please read the [[Short guide to make cabinets]]
## I made my first cabinet! I want to share it with the world!
You can sell it or ask for donations on itchio. Or you can just share it with the community by posting it on Discord. Don't keep the cabinets for yourself, share them somehow!
## I have the cabinet, but the game don't runs, what can I do?
Read the ROM section in this document.
## I upload a cabinet, but I can see it.
The game deploy the cabinet in a free place, search for it.
If you can't find it, be sure you have enough space in the gallery to add new cabinets.
## My gallery is full of cabinets, what I can do?
Just wait for the next version, new versions comes with new rooms.

# Rooms
## What is a room?
The place where you can see the cabinets are called "rooms".
## What is the workshop?
A special room. If you are a cabinet artist or developer is the place where you test the cabinets.
## Can I configure the rooms?
Yes, you can change a little the room, read the configuration documentation: [[AGE configuration using files]]. More configurations to come with new versions in the future.
## How I move from a room to another?
Just walk to the black door and wait for the next room to deploy.
## You can make that all the rooms are available at the same time? it is weird to wait.
Quest can't process all the rooms with all cabinets and introduction videos at the same time, so it's a way to have a big arcade gallery without problems.
## I can't enter a room!
Usually AGE comes with doors to rooms that would exist in future versions. You can't enter there because the room don't exists yet.
## I have to walk a lot to reach a game, can I just jump to it?
No, you can do it, you need to walk as you do in old times. Other options will appear in the future



