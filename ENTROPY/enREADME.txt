F1 - options
F5, F6, alt+enter - fullscreen
F12 sends you to main menu

Clear the game 1 time to unlock Ending 1
Clear the game 5 times to unlock Ending 2
Clear the game 10 times to unlock TRUE PAIN MODE
Clear the game 50 times, at least ONCE as each Character to unlock the secret Character.

https://discord.gg/qrnmJpVKuB Join our community to contribute to LISA. ENTROPY. RPG!

KNOWN ISSUES WITH LCM FIX (and or lcm itself); if anybody is well versed in Ruby and/or RPG Maker VX Ace scripting can figure these out, I'll be very thankful!
1. Party members that are snapped to your position from a rope keep the rope graphics for 1 instance of movement (there was an operator that somehow remedied this but executing it causes crashes).
1.1. POTENTIALLY add LCM FIX calls for when the player character is on a rope???
SOLVED??? 2. If party members think they're about to perform a "game over" jump and they will get snapped to your position, they will refuse to follow the direction that they consider to cause the game over, usually it's the direction your proceeding in. 
SOLVED??? (modified lcm itself) 2.1. I tried to add a check that also prevents LCM fix from being executed if that will be the case (line 4063) && @lcmGameOverCaused == false    BUT alas, it does not work well.
3. When snapped to your position, party members may rarely clip through the ground while performing a jump they somehow buffered into their memory still, bypassing the memory reset.
4. Shifting the memory dump code to "@PREfuturestep" and "@MEGAPREfuturestep" conditions of the player disallows memory restore code from executing later on. 
4.1. This should help with issue 3 somewhat.

KNOWN ISSUES (not lcm, nor lcm fix related)
1. When a party member dies (note: DIES, no K-O, DEATH!) and has a status effect "wheel", which is activated when a party member has more than 4 status effects, the "wheel" is not disposed and persists on battle UI window as a ghost status effect "wheel".
SOLVED??? 2. Text boxes appear scuffed when in-battle. (should have small sizes and only be set to large on VICTORY SCREENS instead they're large always.)