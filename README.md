# Header H1
Header H1 is used to display the Project heading. 

## Sub Topic Headings H2
Sub Topic Headings H2 is used for sub sections like Configurations, Authors etc.

````
pip install boto
````
# Minecraft Skript Guide

### Helpful links for all things skript:<br>
&emsp;SK Unity Discord Server: https://discord.gg/a5DhNQDM<br>
&emsp;SK Unity Skript Documentation: https://docs.skunity.com/syntax/<br>
&emsp;Skript Documentation: https://en.njol.ch/projects/skript/doc<br>
<br>
<b>Effect: Cooldown</b><br>
For implmenting a cooldown on any item effect or command, you will want to use variables to track the cooldown for each player. A good way to do this is to check if the variable related to your cooldown has ever been set for the player, and if it isn't set, we set the cooldown to false meaning the item/command is not on cooldown. This is seen on lines 1 and 2. From here on out, the player's cooldown variable for this item/command will always be true or false, so we need to check if the variable is currently true or false. Obviously, if the cooldown is false we can apply the desired effect like shooting a fireball or allowing the player to teleport. Although, if the cooldown is true we will want to notify the player that they have used the ability too quickly after the last and will need to wait to use it again.
````
if {cooldown.atherwand.%player%} isn't set:
    set {cooldown.atherwand.%player%} to false
if {cooldown.atherwand.%player%} is true:
    send "&7This item needs to cooldown for 7 seconds" to player
if {cooldown.atherwand.%player%} is false:
    set {cooldown.atherwand.%player%} to true
    shoot fireball from player at speed 2
````

 
