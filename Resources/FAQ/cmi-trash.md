# FAQ - How do I create a trash feature in CMI?

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

Note: Since CMI version 9.0.3.x you can create your own .yml files and store them in the `~/plugins/CMI/CustomAlias/` directory.

Note: Per 9.0.4.x the Alias.yml actually has a toggle for `/trash`, you can skip the below CustomAlias.yml step then if you're on the latest version. I will soon(tm) adjust the instructions on this FAQ page.

---

## <g-emoji class="g-emoji" alias="information_source" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png">ℹ️</g-emoji> CMI Dispose (Trash)

- Buy the [CMI](https://www.zrips.net/cmi/) premium plugin if you haven't already, and Install it on all your servers: <https://www.spigotmc.org/resources/3742/>
- Note: CMI requires the [CMI-Library](https://github.com/mrfdev/CMI/edit/master/Resources/FAQ/cmi-library.md) .jar, you can get it here: <https://www.spigotmc.org/resources/cmilib.87610/>


**Introducetion to Dispose**
CMI has a dispose feature, we can use this to dispose of items, if you want a trash bin, trash command, or both, this FAQ entry will walk through it. This is meant as an example to learn how to create your own features using CMI, without the neeed of other plugins, etc.

What we wish to achieve is a sign that players can right click that opens the menu, and a command like /trash that they can type that opens it. Optionally control permissions, configure the dispose command, etc. 


**Permissions**
If you want to control it through `asConsole!` you can skip the Alias.yml and Permissions customization, but for completion I will include it. 

In the console you could type:
```
> cmi checkperm dispose
 1. cmi.command.dispose.others - Dispose of unneeded items
---->When command is used on another player<----
Base command required
 2. cmi.command.dispose - Dispose of unneeded items
```
And we see that in order to give players access to `/cmi dispose` that we need `cmi.command.dispose` you could add this through LuckPerms (permission manager) like so:
```
lp group default permission set cmi.command.dispose true
```
Optionally you could give the admin group the .others permission to manage disposing items on another player. But I doubt you really ever need that. Oh, and no need to restart or reload anything, LuckPerms permission updates are basically instant.


**Alias.yml**
If you want to have this base command be accessable without the /cmi prefix, so `/cmi dispose` becomes `/dispose`, then open the `Alias.yml` file and set the value for /dispose to true, like this:
```
  # /cmi dispose $1-
  /dispose: true
```
You can save the file and either restart the server or at least do a `/cmi reload`


**Okay, let's get to the trash part**

You might notice that the above is about the Dispose feature of CMI, and now we want to use that to add a `/trash` command. 


**CustomAlias.yml**
Either in-game through `/cmi aliaseditor` you can add a new alias command called `trash` and add the command(s) to it: `asConsole! cmi dispose [playerName]`, or you can open `CustomAlias.yml` and at the very end, add the following on a new line:
```
  trash:
    Cmds:
    - asConsole! cmi dispose [playerName]
    Tab: false
```
Now, one note to make here. If you skip the above permission and alias section, you can use it like this. If you for some reason know you want to check 'per group' if they can use dispose, based on that permission, change it to `cmi dispose` instead. I hope that makes sense. The asConsole! part ignores the permission check and they can all use /trash regardless of permissions.

Okay, the command will be live right away, especially after a `/cmi reload`, it will remain Red until you restart the server (so it can properly register the new command).


**Trash Sign**
If you also want players to type `[trash]` on a sign that turns it into a trash bin for them to right click (which will then open the gui to cmi dispose) then go in-game and type this:
```
/cmi ic new trash
```
An in-game chat interface comes up, click on `[Not Public]` which changes it to a Public sign so everybody can use it using a particular permission.

If you want it 100% public, click on the green `[ReqPerm]` will remore the permission requirement. It should now show a grey text saying 'ReqPerm' instead of a green one.

Then click on the green `+` with hover text 'add block you are looking at', you should see particles around the sign now.

Now click on the orange exclamation `!` with hover text 'switch to command editor', you should get a new + and ! in the chat. 

Click on the green `+` with hover text 'add new', and as command, enter:
```
click:rightclick! asConsole! cmi dispose [playerName]
```
And again, please note that if you wish to check per group for those permissions, maybe just use `cmi dispose` instead.

Okay, we're basically done. But let's help the user identify they're using an official server trash bin by changing the text on the sign. There's a button in orange called 'EditSignLines', click that.

Click on the first line, there should be 4 max. `[Empty Line]`, and type:
```
{#magenta}[trash]
```
And maybe click on the second line saying Empty Line, and type 
```
~ ~ ~
```
And maybe the third and fourth one can be to give them a warning:
```
{#orange}Warning:
{#black}There's no undo!
```

Okay, we're basically done. The sign should work right away now. If you didn't make it public you might need to grant the appropriate groups the permission `cmi.interactivesign.trash` to give them access to make these trash signs.

To double-check your configuration, you could open `interactiveCommands.yml` and find the trash: section, it should look something like this:
```
trash:
  Locations:
  - world;12032.0;65.0;19098.0
  - world;-12601.0;63.0;-12149.0
  Commands:
  - click:rightclick! asConsole! cmi dispose [playerName]
  SignLines:
  - '{#magenta}[trash]'
  - ' ~ ~ ~ '
  - '{#orange}Warning:'
  - '{#black}There's no undo!'
  Public: true
  ReqPerm: false
```
*Note: The world and xyz location obviously looks differently.*


**RegEx config**

Okay, before they can start using `[trash`] on a sign, we have to make an adjustment to the cmi `config.yml` file. Changing it away from `[ic:trash]`. Open the yml file and find the follow section: `InteractiveCommands:` and set the regex value to this:
```
InteractiveCommands:
  # Regex used in recognizing public interactive commands used in signs
  # Default format is [ic:[icName]] in example [ic:trash]
  # If you want clean format use regex like: (\[([a-zA-Z0-9]+)\])
  SignRegex: (\[([a-zA-Z0-9]+)\])
```

Save the `config.yml` file and do a `/cmi reload`, you can now have a player test this if you want.


**Done!**

Okay, we're done. Players can now use:
```
/cmi dispose
/dispose
/trash
```
They get a GUI where they can dump their inventory in to dispose of their items. 

And they can now also place a sign and type `[trash]` on it. Then it should change the way the sign looks to those lines we've set. And when they right click on the sign it should open the dispose interface. 

---
