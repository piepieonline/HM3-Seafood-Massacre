# Notes
* Food:
  * Dropping the item gets weird... Item goes to the sky
  * Sometimes item isn't chained!? (Investigate signalpipes?)
  * need to stop them eating if the bowl is destroyed. (Maybe not possible, not getting fracture events :()
* Does ConsumeFromInventory work on AI?
* Bartender
  * If anything happens between bartender picking up bowl and serving them all, he stands there broken - can't replicate
* Sniper
  * Convert to a new entity
  * Needs to fire in open combat
  * Tweak the watch and killzones
  * No longer looking at HM when aiming?
  * Confirmed, if Sniper has shooting memory then his gun will no longer work on NPCs
* PZ Panic. Note: Contacts aren't valid targets - just can't leave with them alive. Force loss of SA and cleanup
 * Need to check they made it inside the building before they panicked? (Maybe not)
 * Sending contract event
 * PZ spreading also for Red's body
* Lock the gate to the back of the restaurant?



* Remove test items (serving plate, poison)
* Fix amulet place (delivery) position & rotation
* Unset default spawn

* First guard deletion override: b4f0676d7f99568a

* trying to get Hokkaido oriental music to play in restaurant?


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