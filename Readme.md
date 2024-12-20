# Bear instead of Meow for BetterChat

To replace your kitty meow emote with a bear wave (close trackmania first):

1. download my modified [BetterChat.op](https://github.com/ReedyBear/tm-better-chat/raw/refs/heads/replace-meow-with-bear/BetterChat.op) that has the kitty images replaced with bear images.
2. Then navigate to `C:\Users\your_user_name\OpenplanetNext\Plugins`. (*If you can't find this folder, open the OpenPlanet menu in TM & open the plugins folder from there*)
3. Cut the original `BetterChat.op` and paste it in a different folder to back it up
4. Paste the newly downloaded `BetterChat.op` into this `Plugins` folder.

Now when someone types "meow" in chat, you'll see the bear wave instead of the kitty meow! However, other people will not see this change.

Hopefully BetterChat team will integrate [my changes](https://github.com/codecat/tm-better-chat/pull/80) so everybody can have bear.

![bear waving gif, four frames](.github/BearFrames.png)

# Better Chat
Complete replacement of the Trackmania in-game chat for [Openplanet](https://openplanet.dev/).

![](.github/screenshot.png)

# Features
Better Chat is better in a lot of ways, with features such as:

* Built-in emotes
* Easier to read names and club tags
* Right-clicking player names for options (spectate, Trackmania.io profile, block, etc.)
* Highlighting on @ mentions
* Custom chat commands
* Autocompletion for mentions, emotes, and commands
* Blocking & filtering
* Streamer mode to censor some bad stuff

# Server controller formatting
When a player with Better Chat connects to a server, the following command is automatically typed into chat:

	/chatformat json

You may choose to ignore this command, or handle it. Additionally, you should handle `/chatformat text` to reset it back to the default formatting.

When you handle the command and the format is set to json, every (chat) message you output to the chat, should be in a Json format prefixed with `CHAT_JSON:`. Below are some example lines.

	CHAT_JSON:{"login":"c5jutptORLinoaIUmVWscA","text":"I'm chatting w/o a nickname!"}
	CHAT_JSON:{"login":"c5jutptORLinoaIUmVWscA","nickname":"Nimz|Miss","text":"I'm chatting with a nickname!"}
	CHAT_JSON:{"text":"This is a system message."}

Additional parameters may be added to Better Chat's display if desired. [Please open an issue](https://github.com/codecat/tm-better-chat/issues/new) if you want Better Chat to display anything from a custom parameter inside of this Json object.

Currently, the following Json object values are handled:

* `login`: The user's login. Only required if this is a chat message from a player. When the login is not provided, it will be displayed as a system message.
* `text`: The text of the message. Required.
* `nickname`: The player's nickname, if set. This is optional.
* `clubtag`: The player's clubtag, if set. This is optional.
