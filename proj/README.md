## Programming Language:
- Assembly on PEPE 16, a special 16 bit processor for education

## Project Description:
In the coming decades, humanity will continue its exploration of the solar system, taking astronauts where no one has gone before. The goal of this project is to create a simulation game of interplanetary travel, featuring a spaceship crewed by intrepid astronauts venturing beyond Mars, navigating through the asteroid belt located between the orbits of Mars and Jupiter.

This zone is perilous due to a high number of asteroids, and it is crucial to avoid a collision, which would be fatal. It is possible to launch a probe with a missile to destroy an asteroid, but this consumes precious energy. However, some asteroids contain valuable metals and compounds that can be mined by a robot sent by the ship to increase its energy, essential for the ion thrusters.

The game interface consists of a screen, a keyboard for control/navigation, and a set of displays to show the ship's energy. The image illustrates a possible game start screen.

The simulator's MediaCenter module has various multimedia capabilities, allowing the definition of background images, playing sounds and videos, various pixel-by-pixel image layers, a frontal scenario for signs, etc.

The keyboard allows, by clicking on some keys, the game commands (start, pause, and stop, in addition to controlling the launch of probes that either explode asteroids or mine them to send energy to the ship).

The displays show the current energy of the ship, which varies over time. It decreases gradually simply because the ship is moving (ionic propulsion consumes a lot of energy) and with each probe shot. It increases when a probe reaches a mineable asteroid, and the respective robot generates energy from the asteroid and sends it to the ship.

Each game state (initial, playing, paused, finished, etc.) should have a different background image, video, or sign (frontal scenario, an image with letters and a transparent background) to give a visual indication of the game state.

**Generic Game Description:**
The game generally consists of the following ideas:
- The screen during the game represents the ship's front window (viewed by the astronauts) with a central instrument panel. There are only 3 possible commands (by clicking on 3 different keyboard keys): launch a probe to the left (at 45°), straight ahead, or to the right (at 45°).
- Probes move in a straight line until they collide with an asteroid or go out of the ship's range (maximum 12 movements, one pixel at a time). The image illustrates two probes (purple pixels) launched diagonally, while the probe launched forward hits the asteroid with an explosion effect.
- It is possible to launch probes in all 3 directions concurrently, but in a given direction, a new launch is only possible after the previous one disappears (due to collision or going out of range).
- Asteroids appear from the top of the screen, which can be of two types: mineable (green in the example) or non-mineable (red in the example). The type should be random, with a ratio of 1 mineable to 3 non-mineable. In the case of a probe collision with an asteroid, there is an explosion (visual and sound effect) if it is non-mineable, and a different effect if it is mineable (in the example, the asteroid gradually shrinks until it disappears as it is mined/consumed, with a "nice work!" sound).
- If an asteroid (of any type) is not intercepted by a probe and collides with the ship's (instrument panel), the ship is destroyed, and the game ends.
- At any given moment, there should be 4 asteroids on the screen. When an asteroid disappears (due to explosion, mining, or being lost at the bottom line), another one should appear at the top of the screen with randomly chosen characteristics: type (mineable 25% of the time, non-mineable 75%), column (in the top-left corner, middle, or top-right corner), direction (those from the corners move diagonally at 45° towards the interior of the screen, those from the middle can move vertically or diagonally to the left or right – the latter cannot collide with the ship, but there is still interest in launching a probe to catch the mineable ones to obtain energy). All 5 possible combinations of column/direction should be equally likely.
- The ship consumes energy simply by operating (at a constant rate) and each time it launches a probe. It gains energy for each probe that reaches a mineable asteroid. There is an initial energy (100%) that can rise or fall. If the energy reaches 0, the ship stops working, and the game ends.
- The objective of the game is to prolong it as long as possible, avoiding the destruction of the ship (collision with an asteroid) and the total depletion of energy.
- There are also game control commands (keyboard keys): start, pause, and stop. All should produce sound effects and display a different image

 or video on the screen.
- The game can be played indefinitely, but it must have the option to save the state of the current game and resume it later, even after closing the simulator. This state includes the current energy of the ship, the time elapsed since the start (time in the game), and the configuration of the game (type and location of asteroids, direction of movement, etc.). The save file must be independent of the simulator version, being possible to load it in future simulator versions without problems.
