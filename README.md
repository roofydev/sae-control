# sae-control

The anti-cheat remote switch for the VRChat world **Steal an Egg** (roofydev/StealAnEgg#2053).

Every player's world reads [`checks.txt`](checks.txt) (served at
`https://roofydev.github.io/sae-control/checks.txt`) when it loads and again every 5 minutes.

- A line `watch <key>` (or `off <key>`) puts that anti-cheat check on **watch-only**: it keeps logging what it would
  have done and changes nothing for players. Delete the line to turn the check back on.
- The file can only **lower** checks. No line can turn a check on, make one stricter, or name a player. This repo
  never holds anything about people.
- An empty file, or one that can't be read, leaves every check as the world shipped it.
- Changes reach every instance within about 15 minutes (5 minutes between reads plus GitHub Pages' cache).

Keys and examples are in the comments at the top of `checks.txt`. Its source of truth is
`Tools/AntiCheat/checks.txt` in the world's repo; keep the two in step.
