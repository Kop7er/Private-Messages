**Private Messages** allows players to send private messages to other players.

This a modified version of the [current version on uMod](https://umod.org/plugins/private-messages) (Added Max Characters on the PM command)!

# Permissions

* ``privatemessages.allow`` -- Allows player to send/receive private messages *(if enabled in config)*

# Chat Commands

* ``/pm <name> <message>`` -- Send a private message to player
* ``/r <message>`` -- Reply to your most recent private message
* ``/pmhistory <name>`` -- Show the previous 5 messages of PM with that player

# Configuration

```json
{
  "EnableLogging": true,
  "EnableHistory": false,
  "UseCooldown": false,
  "CooldownTime": 3,
  "UseIgnore": false,
  "UseUFilter": false,
  "UsePermission": false,
  "UseBetterChatMute": false,
  "PmCommand": "pm",
  "MaxCharacters": 300
}
```

# Localization

```json
{
  "PMTo": "[#00FFFF]PM to {0}[/#]: {1}",
  "PMFrom": "[#00FFFF]PM from {0}[/#]: {1}",
  "PlayerNotOnline": "{0} is not online.",
  "NotOnlineAnymore": "The last person you was talking to is not online anymore.",
  "NotMessaged": "You haven't messaged anyone or they haven't messaged you.",
  "IgnoreYou": "[#FF0000]{0} is ignoring you and cant recieve your PMs[/#]",
  "SelfPM": "You can not send messages to yourself.",
  "SyntaxR": "Incorrect Syntax use: /r <msg>",
  "HistorySyntax": "Incorrect Syntax use: /pmhistory <name>" ,
  "SyntaxPM": "Incorrect Syntax use: /{0} <name> <msg>",
  "NotAllowedToChat": "You are not allowed to chat here",
  "History": "Your History:\n{0}" ,
  "CooldownMessage": "You will be able to send a private message in {0} seconds" ,
  "NoHistory": "There is not any saved pm history with this player." ,
  "CannotFindUser": "Cannot find this user" ,
  "CommandDisabled": "This command has been disabled",
  "IsMuted": "You are currently muted & cannot send private messages",
  "TargetMuted": "This person is muted & cannot receive your private message",
  "NoPermission": "You don't have the correct permissions to run this command",
  "HistoryPM": "[#00FFFF]{0}[/#]: {1}",
  "Logging": "[PM]{0}->{1}:{2}",
  "MaxCharacters": "The private message you attempted to send is too large! Max: {0} characters" 
}
```

# For Developers

### Hooks

```cs
object OnPMProcessed(IPlayer sender, IPlayer target, string message)  // Called before a PM/Reply is sent
//Returning a non-null value overrides default behavior
```

### API Methods

```cs
//Adds to the history of who PM'ed who.
void AddPmHistory(string initiatorId, string targetId)

//Adds to the users PM history & adds to logging.
void AddHistoryAndLogging(IPlayer initiator, IPlayer target, string message)
```

# Credits

* **MisterPixie**, for the current version of this plugin
* **PaiN**, for the original version of his PrivateMessages plugin
* **Nogrod**, for the original version of his PrivateMessage plugin
