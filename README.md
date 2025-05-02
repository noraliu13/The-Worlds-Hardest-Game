# The-Worlds-Hardest-Game

This project is a recreation of the popular online game _The World's Hardest Game_, originally
hosted on Cool Math Games. Implemented in the C programming language, the game
consists of two challenging levels where the player controls a red block and must navigate
through moving blue obstacles and collect yellow coins to reach green safe zones. The game
runs on the Nios V processor and is displayed via VGA output, and the speakers, through the
DE1-SoC board. Input is provided through a PS/2 keyboard, using either the WASD or arrow
keys for movement.

The player is greeted with a custom-designed main screen, created in Canva and converted to
a C array using a PNG-to-C converter. The game begins when the user presses the spacebar.

In **Level 1**, the player starts in a green zone and must reach the ending green zone while
avoiding blue-moving obstacles. Upon reaching the end, the game proceeds to Level 2, which
introduces coin collection. In **Level 2**, the player must collect all yellow coins before reaching the final green zone.

Each level map, including tiles, the player, obstacles, and coins, is rendered at the pixel level.
All dynamic game elements (player, coins, and obstacles) are erased and redrawn pixel by
pixel to simulate movement. Colliding with a blue obstacle triggers a **death sound**,
increments the **death counter**, and respawns the player at the starting green zone. If the
player dies before collecting all coins in **Level 2**, the coin positions **reset**, and the death
counter increases. When a coin is collected, a **coin sound** plays, and the coin counter
increments. **Collision detection** is achieved by reading the colour of pixels from the VGA
buffer to determine if the player has hit an obstacle, coin, or boundary. This allows for precise
handling of all interactions between the player, obstacles, and collectible items. The player
must collect all coins before entering the final green zone to proceed to the **end screen**,
which plays concluding music. Finally, the player can return to the main screen by pressing
the **Escape key**.
