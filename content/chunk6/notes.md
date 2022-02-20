# RUDDY'S NOTES
- Can we please finalise whatever's going on with the plate version of the amulet? Everything else is being finalised now, I think we're beyond having a floating plate in the air.
- Chief is now incapable of actually entering combat with you, because combat state triggers his evacuation. This means I may as well make him a civillian (And the other targets when I get around to them)
- Nobody actually follows chief if he evacuates after that specific guy stops following him, this must be recitified. I'll try.
- Waiting for QN patch maker to work so I can revert scenario_noodle back to vanilla but KEEP my different parentings (I'll do this)
- I will totally re-do (add in) a lot of trespassing zones, don't worry about that
- The bartender cannot have a weapon visible the whole time, it needs to be a surprise. I'd love the sawn off to be hidden in his 'pocket'. Worst case is he has a pistol, but pistol is shit and not what he has in the original missions.
- Atampy's been working on some really cool stuff with randomised routes/acts; I'd love to put one or two civillians in the streets and alleys who do this
- I've made the ICA apartment a viable alternative sniping spot, but I will put an NPC in there so there's some challenge
- Need to make chief, bartender and sniper not respond to distractions or help civilians. I should be able to do this.
- Need to delete that annoying fucking 'have yu seen a gir aroun' lady
- I still have more cop variations to make, and the associated nude variations, it's not at the top of my list.



Possible ideas - Undecided:
- Do something with The Block now that it's empty? I was just going to move the homeless in there, but I'm open.
- C47 music for the daytime version of the mission (This one should be easy because C47 didn't have combat themes or anything, it play the one 7 minute track everywhere, permanently) and Contracts music for the night version of the mission (Harder because it has combat themes, etc)

Future Easter Eggs:
- Make the ICA Facility start in meltdown. A new keypad with some sort of special code will be placed on the map and allow access. Inside will be Dawood Rangan dancing to music. You get the meltdown started and I'll do the rest.
- The answering machine in ICA apartment... instead of the End Of Era story shit it's gotta play something funny
- A girl with shoh hair and bright green bag. I'll make this lady, don't worry. Hopefully she can be one of Atampy's randomised people.



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
  * AIModifieractor, no lure
* Panic needs to be if they get to a guard, not just out of zone? (...or like PZ? Spreads to anyone they contact? But contacts aren't valid targets - just can't leave with them alive. Force loss of SA and cleanup)
 * PZ also for Red's body
* Lock the gate to the back of the restaurant?
* Targets should evac?



* Remove test items (serving plate, poison)
* Fix amulet place (delivery) position & rotation
* Unset default spawn

* First guard deletion override: b4f0676d7f99568a

* trying to get Hokkaido oriental music to play in restaurant?

To reenable planning contract changes (Pie only)
git update-index --no-assume-unchanged content\chunk0\planning_contract\00F999C5DA38B5BD.JSON

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