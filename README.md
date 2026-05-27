# Week 3 Example 2: Full Fighting Game

## What This Example Demonstrates

> **Note for students:** This section is included in example files only to help you study. Do not include it in your Side Quest submissions.

This example builds on Example 1 by adding health, attacking, hit detection, sound, and game states to create a complete two-player fighting game.

- **Game states** — the game is always in one of three states (`STATE_START`, `STATE_FIGHT`, `STATE_WIN`); each state controls what gets drawn and what responds to input; stored as constants to prevent typos
- **`preload()`** — loads all sounds before the sketch starts so they are ready to play immediately; sound files are loaded into an array for variety
- **Sound array** — `punchSounds` holds all 9 punch sounds; `floor(random(...))` picks a random index each time a punch lands so hits sound different
- **Health system** — each fighter has a `health` property that decreases when hit; `maxHealth` is stored separately so health bars can be drawn proportionally using `map()`
- **`startAttack()`** — called from `keyPressed()` so the punch fires once per press; sets the direction of the fist based on the opponent's position
- **`getPunchX()`** — a method that returns the fist's x position; used in `checkHits()` to test whether the punch connects with the opponent
- **`takeHit()`** — called on the fighter being hit; blocked punches deal no damage; health reaching zero triggers `endGame()`
- **Hit flash** — `hitFlash` counts down from 12 each time a fighter is hit; while it is above zero, the blob draws white instead of its normal colour
- **`hitLanded` flag** — prevents the same attack swing from registering more than one hit per punch
- **`keyPressed()` vs `keyIsDown()`** — `keyPressed()` fires once per press and is used for attacks and menu navigation; `keyIsDown()` fires every frame and is used for movement and blocking
- **Health bars with `map()`** — `map()` converts health (0 to maxHealth) to a bar width in pixels (0 to barW); the bar shrinks as health decreases
- **Start and win screens** — drawn using text and shapes in their respective game states; a semi-transparent overlay is used on the win screen

## Setup and Interaction Instructions

To run the sketch locally, open `index.html` in Google Chrome using Live Server.

Sound files must be present in `assets/sounds/` before running:

- `punch_1.wav` through `punch_9.wav`
- `win.wav`
- `background.mp3`

**Player 1 Controls:**

- Move: A / D
- Attack: F
- Block: G

**Player 2 Controls:**

- Move: Arrow Keys
- Attack: K
- Block: L

Press **ENTER** to start or rematch.

**Opening the Chrome Console**

- **Windows:** Press `F12` or `Ctrl + Shift + J`, then click the **Console** tab
- **Mac:** Press `Cmd + Option + J`

The console will show any errors in your sketch.

## Assets

| File                                        | Source                                            |
| ------------------------------------------- | ------------------------------------------------- |
|  "assets/sounds/203_SQ3_Music.mp3"[1]       |  freemusicarchive, Lunch by Podington Bear - freemusicarchive.org                                                                              |
| `assets/sounds/win.wav`[2]                  | listener4me, Win Sound Effect — OpenGameArt.org   |
| "assets/sounds/302_hit_bang.mp3"[3]         | pixabay, Bang Sound Effect - https://pixabay.com                                                                                               |
| "assets/images/203_SQ3_Background.webp".[4] | shutterstock, Pixel art game level background with a city skyline - https://www.shutterstock.com                                                       |
| "assets/images/302_SQ3_VictoryBG.jpg"[5]    | istockphoto, Winner's Cup — istockphoto.com       |
| "assets/images/203_SQ3_StartBG.jpg"[6]      | vecteezy, Modern city scape silhouette vector — vecteezy.com                                  |                                                   |
| "assets/images/203_SQ3_Hit_BG1.webp"[7]     | dicebreaker, Dixit, Dobble, Unlock! and more family board games released as free print-and-plays to download at home — dicebreaker.com                |
| assets/images/203_SQ3_Hit_BG2.png[8]        | screenwiseapp, How to Play Dixit with Mixed Ages: Tips for Family Game Night — screenwiseapp.com                                                    |


## References

[1] Anon. Lunch. Retrieved May 27, 2026 from https://freemusicarchive.org/music/Podington_Bear/Background/Lunch/ 
[2] listener4me. n.d. _Win Sound Effect_. OpenGameArt.org. Retrieved May 1, 2026, from https://opengameart.org/content/win-sound-effect
[3] Anon.Retrieved May 27, 2026b from https://pixabay.com/sound-effects/search/bang/ 
[4] Anon. 7,419 pixel video game background illustrations. Retrieved May 27, 2026a from https://www.istockphoto.com/illustrations/pixel-video-game-background 
[5] Anon. Winner’s Cup, symbolizing victory and success in competitions. First... Retrieved May 27, 2026c from https://www.istockphoto.com/photo/winners-cup-symbolizing-victory-and-success-in-competitions-first-place-prize-trophy-gm2157551537-578234312 
[6] Haidir Ahmad. Modern city scape silhouette vector. simple minimalist blue city skyline background. urban cityscape silhouettes vector illustration. Retrieved May 27, 2026 from https://www.vecteezy.com/vector-art/22737904-modern-city-scape-silhouette-vector-simple-minimalist-blue-city-skyline-background-urban-cityscape-silhouettes-vector-illustration 
[7] Alex Meehan. 2020. Dixit, Dobble, unlock! and more family board games released as free print-and-plays to download at home. (April 2020). Retrieved May 27, 2026 from https://www.dicebreaker.com/companies/asmodee/news/dixit-dobble-unlock-released-as-free-print-and-plays 
[8] Screenwise. How to play Dixit with mixed ages: Tips for Family Game Night. Retrieved May 27, 2026 from https://screenwiseapp.com/guides/how-to-play-dixit-with-mixed-ages-tips-for-family-game-night 