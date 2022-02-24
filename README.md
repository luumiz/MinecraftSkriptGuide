# Minecraft Skript Guide

### Helpful links for all things skript:<br>
&emsp;SK Unity Discord Server: https://discord.gg/a5DhNQDM<br>
&emsp;SK Unity Skript Documentation: https://docs.skunity.com/syntax/<br>
&emsp;Skript Documentation: https://en.njol.ch/projects/skript/doc<br>
<br>
<b>Variables</b><br>
For those that are not familiar with other code languages, variables are used to store data throughout the lifespan of a skript. These are integral to utilizing Skript to it's mazimum potential. For example, variables can be used to hold any data in memory.<br>
1. Local Variables<br>
&emsp;Local variables are defined with the syntax {_localVariableName}. These are only able to be referenced within the scope they are defined in. For instance, if you declare a local variable inside of a loop or if statement, that variable will not be able to be referenced outside of the loop or if statement. In the code below, the {_insideLoop} local variable will not be able to be referenced outside the loop.
````
if {%player%.isTrading} is true:
    send "currently trading"
    if clicked slot is 1 or 2 or 3 or 4 or 5 or 6 or 7 or 8:
        set {_checksender} to false
        # outside loop
        set {_countsender} to 1
        loop {tradingsender::*}:
            # inside loop
            if name of slot 0 of player's current inventory is "%{tradingsender::%{_countsender}%}%":
                if name of player is "%{tradingsender::%{_countsender}%}%":
                    set {_checksender} to true
                    set {_insideLoop} to true
                    send "sender clicking on his slots"
                    exit 1 loop
            else:
                add 1 to {_countsender}
        if {_checksender} is not true:
            send "reciever clicking on sender's slots"
            cancel event
````
2. Global Variables<br>
&emsp;Global variables are defined with the syntax {globalVariableName}. These are able to be referenced throughout an entire skript as well as all other skript on a server. 
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

 
