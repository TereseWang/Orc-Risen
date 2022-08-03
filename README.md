# Orc-Risen (Not for commercial use)
### GAME DESCRIPTION
ORC Risen is a tactical rogue-lite game. Players will play the role of a small orc clan chief. As the chief, the player needs to recruit their own orc army, and build the clan over time to defeat the coming human adventurers and crusaders. If the player’s clan is defeated, they will start the entire game over.
### WEBGL EXPORT
- https://zhijianwang.itch.io/cs3540-final-project
### REPOSITORY
- https://github.com/zljtt/CS3540-final-project
### GAME ASSETS
- Map: https://www.artstation.com/marketplace/p/a19mM/voxel-orc-castle-asset - Portal:https://assetstore.unity.com/packages/vfx/particles/portal-particle-effect-106952 
- Effect:https://assetstore.unity.com/packages/vfx/particles/stylized-aoe-magic-spells-vol-1-173230
- UI: https://assetstore.unity.com/packages/2d/gui/troll-nest-mobile-ui-kit-159645 
- Dragon:https://assetstore.unity.com/packages/3d/characters/creatures/poly-hp-dragon-177623
- Orc Unit:https://assetstore.unity.com/packages/3d/characters/creatures/minions-series-orcset-202730 
- Human Unit:https://assetstore.unity.com/packages/3d/characters/humanoids/hero-series-adventurers-139707 
- Music:https://assetstore.unity.com/packages/audio/sound-fx/weapons/medieval-combat-sounds-149395\ 
- Projectile: https://assetstore.unity.com/packages/vfx/particles/spells/toon-projectiles-158199
           
### Audience
The game focuses on the players who like rogue-lite games and turn-based strategy games. It seems like the game is based on city building and planning, but we do not expect the audience from this perspective, since sometimes the player will be defeated and have to start over again keeping nothing. The game also uses voxel arts for all resources, which will attract players who like pixel arts.
### Background and Characters
In a world with a variety of races blessed by God, the orc is one of the weakest since they believe in their own ancestries rather than God. Most races, especially humans, hold the perception that orcs are aggressive, strange-looking, and non-rational. They believed that orcs are evil, thus for their sack of ‘justice’, they invaded orcs' clans. The player will inherit the clan from the old chief, who died from the invasion of crusaders of a nearby human kingdom. To defend the clan from the adventurers, who aim for the myths and treasures of the clan, the player will build the city and get ready to fight.
### Objectives
The objective of the game is to defend the castle from the adventurers by deploying orc soldiers until no enemy attacks. When the player's power is recognized by the surrounding authorities, a peace treaty will be signed to demonstrate the victory of the clan.
### Game Progression
The player starts with a basic castle with minimal facilities and progress in the following order:
1. The player will start off in a battle against some enemies who are adventurers from the human kingdom. The enemies will start off weak, similar to the player. After defeating waves of enemies, the player will gather money, items, and other loot, which can be used to upgrade their castle and/or their units in-between battles.
2. Enemies will grow stronger as the player does. After hearing the death of many adventurers, crusaders from the human kingdom will come. Crusaders are elite enemies with stronger power, which can be seen as the boss fight for each level. After each crusader fight, stronger adventurers will come. This process will repeat.
3. Eventually, the player will build up the clan into a kingdom, and face the final wave of crusaders. If they defeat it, the human kingdom will admit the orc kingdom’s power, and sign the treaty of peace. Else the entire game will start over.
### Systems (Game Rules)
Game mechanics / features:
- Player
    - First person movement

 i) Allow user control players by pressing WASD/arrow keys.
ii) The player can also jump by pressing space
b) Inventory for placing ally units or using healing potion
i) The player can use the number key from 1 to 9 and 0 to use certain
items in the slots.
ii) When potion is used, generate particle effects and heal ally units.
iii) Items/skills has cooldown
iv) Use ally units spawner to place an ally onto the battlefield.
c) State persistency for the player data
i) store the player progression and inventory into file
ii) read files into the data as a game starts or a scene loads
2) Units
a) FSM system for enemy and ally unit AI.
i) The states change from IDLE/ALERT/CHASE/ATTACK/DIE for most units and RISE for drake.
ii) During the PLANNING phase, all units are IDLE.
iii) As the COMBAT phase starts, all units become ALERT. Enemy units
will walk to the target warp point. Ally units will stay and wait for the
enemy to come.
iv) If a unit finds a target to attack during ALERT, it will enter CHASE to
try to reach the target.
v) As it reaches the target, it enters ATTACK until the target leaves the
attack range.
b) Mesh navigation of units
a) Enemy will find the best route towards the portal automatically avoiding the obstacles. If there are ally units around, it will also attack them before moving to the portal.
b) Ally units will stand in the fix point if there is no enemy within the alert range. If there is a target, the unit will try to move and attack them.
c) Integrate mesh nav movement into FSM system.
c) Current implemented Units
i) Orc Soldier: Using axe to attack encountered enemy.(Most Common way to attack, level one unit)
ii) Orc Wizard: Shooting Magic Ball(Projectile) to attack.(New Distanced Attacking strategy, level two unit)
iii) Junior Dragon: Shooting Fireball(Projectile) to attack.(New Distanced Attacking strategy, level two unit)
iv) Orc Archer: Shooting Lighting Arrow(Projectile) to attack.(New Distanced Attacking strategy, level three unit), lower moving speed with high performance on shooting.
v) Orc Fighter: Using sword to attack ebcountered enemy. With higher amount of health compare to orc soldier. But dealt less damage to enemy with slower speed.
item, coin and ritural
d) potion,
a) Healing potion can befound when enemy is killed or purachsed in
store, with the ability to heal singla unit small amount of health

 b) Mass healing can befound when enemy is killed or purachsed in store, with the ability to Heal all ally units in 5 radius by 10% max health over 2 seconds.
c) Encourage spell can befound when enemy is killed or purachsed in store, with the ability to Encourage target ally unit, increase its attack damage and max health by 20% for 20 seconds.
d) Taunt spell can befound when enemy is killed or purachsed in store, with the ability to Target ally unit taunts enemies, forcing all nearby enemy units to attack it.
e) Windgrace spell can befound when enemy is killed or purachsed in store, with the ability to Largely increase target ally unit's alert range and movement speed.
f) Rage spell can befound when enemy is killed or purachsed in store, with the ability to Rage target ally unit, increase its attack damage and speed by 50% but losing health over 5 seconds.
g) Wolf Ritual can befound when enemy is killed or purachsed in store, with the ability to Ally units' attack damage increases when there is no other ally units nearby.
h) Health Ritual can befound when enemy is killed or purachsed in store, with the ability to Ally units's max health is increased by 20%.
i) Coin can befound when enemy is killed and use to purchase item in the store.
3) The player can travel between different scenes by using the teleportation door.
a) In the castle, the player can go to each battlefield by using the door at any
time.
b) The player can go back to castle after combat
4) Teleportation door / target to protect
a) There is a teleportation door at the end of the map, when an enemy
encounters the door, the player loses life. If the player does not have enough
life, they lose.
b) Attacking Path Indicator shows up when the player is in the preparation
phase, allowing the player to better realize the route that the enemy is
planning on attacking and place units in response.
5) Main Menu
a) Resume Game Button(Cross UI): Allow players back to game when pressed.
b) Setting Button: Allow players to change mouse sensitivity based on
preference when pressed.
c) Main Menu Button: Back to main menu scene when pressed.
d) Tutorial Button: Allow players to better understand the game rule and concept
when pressed.
e) All the buttons above are well polished with UI fit the theme.

 PLAYTESTING FEEDBACK We notice that there are two major feedback from playtesting
● Hard to know what to do next
○ To solve that, we add a mandatory guide each time the player enter the
castle, introducing the basic control and what they can do. ● Player can do nothing in combat
○ To solve that, we increase many items and spells for the player to use in combat, for example healing potion and taunt spell.
CONTRIBUTIONS
There are so many scripts and words in this project, so we simplified the contribution chart.
    Script/Component
Contributors
Code/Scene intergratation
Zhijian
Items
Zhijian and Hongyi
Player Controll
Bitan and Hongyi
Particle Effect
Bitan and Haoqing
Animation
Bitan and Haoqing
Unit Design
Zhijian
Unit Script
All group member
Main UI Design
Haoqing
Main UI Script and prefabs
Haoqing and Bitan
Combat UI
Hongyi and
Store UI and store
Zhijan
Inventory UI and store
Zhijian and Hongyi
Scene Building
Zhijian
Documentaiton
Zhijian and Bitan
Item texture
Bitan
Some models
Bitan and Haoqing
                 
PLAYTEST TIPS
Control:
WASD/Arrow Key: move horizontally
Space: jump
number key (1,2,3,4,5,6,7,8,9,0): use item including unit spawner and spells open store in castle : p
open inventory in castle : tab / q
end the preparation phase in combat: p
pause and menu : esc
Others:
Please maximize the screen while testing in itch.io, the pause screen behavior is very strangely during combat, please modify the sensitivity in castle.