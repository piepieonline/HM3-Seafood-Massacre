# Notes
* Food:
  * Dropping the item gets weird... Item goes to the sky
  * Sometimes item isn't chained!? (Investigate signalpipes?)
  * need to stop them eating if the bowl is destroyed
  * Add chopsticks
  * Remove chef checking bowl action
* Does ConsumeFromInventory work on AI?
* Set amulet to kinematic
* Sniper
  * Convert to a new entity
  * Needs to fire in open combat
* Panic needs to be if they get to a guard, not just out of zone? (...or like PZ? Spreads to anyone they contact? But contacts aren't valid targets - just can't leave with them alive. Force loss of SA and cleanup)
* Lock the gate to the back of the restaurant?



* Remove test items (serving plate, poison)
* Fix amulet place (delivery) position & rotation
* Unset default spawn





## Overrides
### Property overrides
1. Locked bathroom door
2. Parenting food serving to the new location (OLD?)
3. Bartender is the server
4. Food is ready to serve when bell is rung (1 additional value)
5. Chef serves on timer, but not on the bell
### Pin connections
1. When the food is ready, mark it so (Skip inspection)
2. When the chef finishes serving, start the next serve (OLD?)
3. When the food is ready, grab a reference to it (for poison transfer)
4. When the serving is complete, complete the drama proxy
5. Skip the chef's 'plate inspection' animation during loop
### Pin deletes
1. The first plate shouldn't complete the drama, have to serve two more (OLD?)
2. Starting our own plate carrying animation, instead of this one
3. Remove the chef inspecting plate animation from the loop