# Minecraft Skript Guide

Helpful links for all things skript:<br>
&emsp;SK Unity Discord Server: https://discord.gg/a5DhNQDM<br>
&emsp;SK Unity Skript Documentation: https://docs.skunity.com/syntax/<br>
&emsp;Skript Documentation: https://en.njol.ch/projects/skript/doc<br>
<br>
<b>Effect: Cooldown</b>
&emsp;```
if {cooldown.atherwand.%player%} isn't set:
                set {cooldown.atherwand.%player%} to false
            if {cooldown.atherwand.%player%} is true:
                send "&7This item needs to cooldown for 7 seconds" to player
            if {cooldown.atherwand.%player%} is false:
                set {cooldown.atherwand.%player%} to true
                shoot fireball from player at speed 2
```

