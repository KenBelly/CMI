# FAQ - CMI Glow Information

<topMenu>
<details>
    <summary><strong>FAQ Menu</strong></summary>
    <p>
     • <a href="https://faq.cmi.support/bungee">Bungeecord-Info</a>, 
     • <a href="https://faq.cmi.support/chance">Chance-Example</a>, 
     • <a href="https://faq.cmi.support/format">Chat-Format</a>, 
     • <a href="https://faq.cmi.support/chat">Chat-Manager</a>, 
     • <a href="https://faq.cmi.support/chatfilter">Chat-Filter</a>, 
     • <a href="https://faq.cmi.support/chatrooms">Chat-Rooms</a>, 
     • <a href="https://faq.cmi.support/commands">Commands-Manager</a>, 
     • <a href="https://faq.cmi.support/joinleave">Custom-Join-Leave</a>, 
     • <a href="https://faq.cmi.support/economy">Economy-Manager</a>, 
     • <a href="https://faq.cmi.support/ext-cmds">Extending-Commands</a>, 
     • <a href="https://faq.cmi.support/gettingstarted">Getting-Started</a>, 
     • <a href="https://faq.cmi.support/glow">Glow</a>, 
     • <a href="https://faq.cmi.support/help">Custom-Help</a>, 
     • <a href="https://faq.cmi.support/hexcolors">Hex-Colors</a>, 
     • <a href="https://faq.cmi.support/import">Importing-Data</a>, 
     • <a href="https://faq.cmi.support/library">CMILib</a>, 
     • <a href="https://faq.cmi.support/prefix">LuckPerms-Prefix</a>, 
     • <a href="https://faq.cmi.support/migrate">Migrate-Database</a>, 
     • <a href="https://faq.cmi.support/mode-stuck">Mode-Stuck</a>, 
     • <a href="https://faq.cmi.support/more-msg-cmds">More-Msg-Commands</a>, 
     • <a href="https://faq.cmi.support/motd">MOTD</a>, 
     • <a href="https://faq.cmi.support/params">Parameters</a>, 
     • <a href="https://faq.cmi.support/ranks">Ranks</a>, 
     • <a href="https://faq.cmi.support/rules">Custom-Rules</a>, 
     • <a href="https://faq.cmi.support/running">Running-CMI</a>, 
     • <a href="https://faq.cmi.support/safety">Safety-Tips</a>, 
     • <a href="https://faq.cmi.support/social">Social-Addon</a>, 
     • <a href="https://faq.cmi.support/specialized">Specialized-Cmds</a>, 
     • <a href="https://faq.cmi.support/toggle">Toggle-Example</a>, 
     • <a href="https://faq.cmi.support/trash">Trash</a>, 
     • <a href="https://faq.cmi.support/votes">Vote-Manager</a>,
     • <a href="https://faq.cmi.support/worth">Worth</a>.
    </p>
</details>

<details>
    <summary><strong>Official Zrips Links</strong></summary>
    <ul>
        <li><a href="https://zrips.net/">Zrips Website</a>
         <pre>https://www.zrips.net/<br>The official website, wiki/documentation/information</pre></li>
        <li><a href="https://discord.gg/dDMamN4">Zrips Discord</a>
         <pre>https://discord.gg/dDMamN4<br>The official Discord community server with member-driven support</pre></li>
        <li><a href="https://github.com/Zrips/">Zrips Github</a>
         <pre>https://github.com/Zrips<br>The place for bug reports and feature suggestions</pre></li>
    </ul>
</details>

<details>
    <summary><strong>Prerequisites</strong></summary>
    <ul>
        <li><a href="https://www.spigotmc.org/resources/3742/">Buy and Download CMI</a> (premium plugin)
         <pre>https://www.spigotmc.org/resources/3742/<br>Get the CMI plugin if you haven't already, and then Install it on all your servers</pre></li>
        <li><a href="https://www.spigotmc.org/resources/87610/">Also Download CMILib</a> (free library) (<a href="https://github.com/mrfdev/CMI/edit/master/Resources/FAQ/cmi-library.md">more info</a>)
         <pre>https://www.spigotmc.org/resources/87610/<br>All Zrips plugins require the CMILib .jar file. Get it and also put it on all your servers.</pre></li>
        <li>All my FAQ pages have been written for Spigot / Paper 1.18.2 and CMI 9.1.3.x or newer.</li>
        <li>The mrfdev github page is not an official resource, we're building up our knowledge base as a courtesy.</li>
        <li>I am an admin on the Zrips Discord, this does not mean what I share on here is official.</li>
    </ul>
</details>
</topMenu>

---

**CMI can use a character Glow color, as well as nameplate colors, etc.**

Hopefully this FAQ helps explain the issues with glow due to conflicting plugins and/or clients.

There's a little cmi glow youtube video I made that you can check out here: https://www.youtube.com/watch?v=6qHk9Po0aAg

---

## <g-emoji class="g-emoji" alias="information_source" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png">ℹ️</g-emoji> CMI Glow

- **Commands**:
```
/cmi glow (playerName) [true/false/color/gui]
```
To use `/glow` directly as a command, update `~/plugins/CMI/Alias.yml` by setting The glow command from `false` to `true`.

Bonus: Rainbow glow colors? No, not by default, but you could make a `/cmi aliaseditor` command that uses the `delay! 0.5` option and runs through all the colors once. Then players could use `/glow rainbow` if they have the correct permissions.

- **Permissions**:
```
cmi.command.glow - Allows players to use /cmi glow command. (Player command)
cmi.command.glow.others - Allow players to set the glow of other players (Staff command)

cmi.command.glow.color.[colorname] - Allows to change glow color, you can * wildcard this, or be very specific.

cmi.command.armorstand.glow - Optionally you can grant a players to make glowing armorstands.
```

- **Placeholders**:
```
%cmi_user_glow_code%
%cmi_user_glow_name%
```

- **Hex colors**:
```
The glow effect does not support hex colors
```

## <g-emoji class="g-emoji" alias="information_source" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png">ℹ️</g-emoji> It isn't working - help

Before we check if another plugin might cause a conflict (see below) we will have to request you to review your current set-up. 
I personally recommend to use Paper 1.17.1 for the best results. But Spigot and Paper both are fine to use. 
Please note that forks of forks of forks could be a reason why glow on your server isn't working. Perhaps check first on a backup/test set-up with Spigot or Paper. 

Next is to double check on SpigotMC if (CMI)[https://www.spigotmc.org/resources/3742/] and (CMILib)[https://www.spigotmc.org/resources/87610/] are both up to date. 

And finally, be sure it's not your client or mods that are causing issues. Use the vanilla launcher and client and use the same version as the server engine. And ask another player to look at your character as you use /cmi glow to make changes.

## <g-emoji class="g-emoji" alias="information_source" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png">ℹ️</g-emoji> It is always white - plugin conflicts

Due to the nature of how vanilla Minecraft is made developers are limited with what we can do/use in regards to using and controlling glow; 
which is done through the name tag prefix. And every plugin tries their best to work correctly. They're trying to stay in control over the features they offer. 
As a consequence you will have multiple plugins conflicting, and when something conflicts and doesn't work you will end up with a non working or white glow, or at least inconsistant results. 

A random example is a popular CMI alternative to tablist.yml called TAB, it lets you resolve the issue by using `%cmi_user_glow_code%` placeholder. More information about that (here)[https://github.com/NEZNAMY/TAB/wiki/How-to-make-TAB-compatible-with-glow-plugins].

A reasonable way to figure out if it's a plugin that's conflicting:
- /stop the server, and back it up. Make a clone of it to test with.
- Start the live server again of course, but not yet the test server.
- Remove all the plugins from the test server - except CMI, CMILib, Vault and start the test server.
- Login and try to use cmi glow again. 
- If it still doesn't work, it might be a client-side problem.
- If it works now, it might be a plugin confict. You can put back all the plugins you think that aren't causing this problem and start, repeat the test. Until you find it to break and then you know which plugin might cause the problem. You can then ask the developer of that plugin to (better) support CMI's glow feature to prevent conflicts.

Known plugins causing conflict:
- TAB
- Scoreboard R4
- know of one? Let me know!

## <g-emoji class="g-emoji" alias="information_source" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png">ℹ️</g-emoji> Misc.

Still having issues and want to report what you believe is a bug with the CMI glow feature? Please open a new Issue on Zrips' Github repository for CMI:
https://github.com/Zrips/CMI/issues

Want to make suggestions to help improve the functionality of the CMI glow feature? Please open a new Discussion on github:
https://github.com/Zrips/CMI/discussions

---
