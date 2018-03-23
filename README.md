# Roids sample game

Welcome to the "Roids" sample game. This is a very simple "Asteroids" clone where you turn the ship left and right with the arrow keys and fire at incoming meteors with <kbd>space</kbd>.

[Play the game!](defold://build)

## Explore the sample

This is how the project is laid out:

* ["main.collection"](defold://open?path=/main/main.collection) is loaded at game start. It ties everything together.
* The flow of the game is controlled from ["main.script"](defold://open?path=/main/main.script). It keeps track of lives and score and sends timed messages to the rest of the game to set things up properly.
* ["player.go"](defold://open?path=/main/player.go) contains the player ship. It runs a script that listens to input, turns and fires laser shots. All shots (["laser.go"](defold://open?path=/main/laser.go)) are spawned dynamically. When the player ship collides it spawns an explosion effect (["explosion.go"](defold://open?path=/main/explosion.go)) and tells the main script what just happened.
* ["spawner.script"](defold://open?path=/main/spawner.script) contains the logic for spawning meteors. It calculates when and where meteors will spawn and sets them in motion by giving them a movement direction and speed. The script also keeps track of every spawned meteor so they can be deleted when the play field is reset on player death.
* ["meteor_large.go"](defold://open?path=/main/meteor_large.go) contains the large meteor type. It rotates and moves. If it detects a collision, it deletes itself but spawns two smaller meteors (["meteor_small.go"](defold://open?path=/main/meteor_small.go)). The two meteor types share the same script. The type is determined by a property set on the script component in each game object file.
* ["hud.gui"](defold://open?path=/main/hud.gui) contains GUI elements such as the lives and score counters, "get ready" and "game over" texts. Its script ["hud.gui_script"](defold://open?path=/main/hud.gui_script) listens to messages to update what to show. These messages are all sent from the main script.

Now spend some time digging around the project. Change and experiment with it.

Here are some ideas what you can try:

1. Add a start screen.
2. Keep track of high score.
3. Add more effects (when the meteors are hit, for instance).
4. Add touch controls so the game can be played on mobile.
5. Add powerups like better weapons, shields etc.

Check out [the documentation pages](https://defold.com/learn) for more examples, tutorials, manuals and API docs.

If you run into trouble, help is available in [our forum](https://forum.defold.com).

Happy Defolding!

----

This project is released under the Creative Commons CC0 1.0 Universal license.

You’re free to use these assets in any project, personal or commercial. There’s no need to ask permission before using these. Giving attribution is not required, but is greatly appreciated!
[Full license text](https://creativecommons.org/publicdomain/zero/1.0)
