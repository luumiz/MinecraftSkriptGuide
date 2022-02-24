# Minecraft Skript Guide

Helpful links for all things skript:<br>
&emsp;SK Unity Discord Server: https://discord.gg/a5DhNQDM<br>
&emsp;SK Unity Skript Documentation: https://docs.skunity.com/syntax/<br>
&emsp;Skript Documentation: https://en.njol.ch/projects/skript/doc<br>
<br>
<b>Effect: Cooldown</b>
&emsp;```if {cooldown.atherwand.%player%} isn't set:<br>
&emsp;&emsp;                set {cooldown.atherwand.%player%} to false<br>
&emsp;&emsp;            if {cooldown.atherwand.%player%} is true:<br>
&emsp;&emsp;                send "&7This item needs to cooldown for 7 seconds" to player<br>
&emsp;&emsp;            if {cooldown.atherwand.%player%} is false:<br>
&emsp;&emsp;                set {cooldown.atherwand.%player%} to true<br>
&emsp;&emsp;                shoot fireball from player at speed 2```

