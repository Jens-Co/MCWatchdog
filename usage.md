---
layout: inner
title: Usage
permalink: /usage/
---

### Server Commands

#### Adding servers

`/server add <alias> <address> <port>`

This is used to add a server to your Discord's saved server list. You're allowed 5 saved servers. All fields are required. 

- `alias`: what you want to name the server
- `address`: the connection address for the server
- `port`: the port for your server (defaults: Java 25565, Bedrock 19132)

---

#### Removing servers

`/server remove <alias>`

Used to remove a server from the saved servers list.
- `alias`: the name used to save the server.

---

#### Set server image

`/server image <alias> <url>`

This allows an image URL to be specified for the server.

---

#### Server List

`/server list`

Lists all of the servers that have been saved to the Discord.

---

<br>

### Embed Commands

#### Enable status 

`/status enable <alias>`

Enables the automatically updating embed in the channel the command is executed in. A server must be saved first using `/server add` to use this feature.

---

#### Disable status

`/status disable <alias>`

Disables the automatically updating embed.

---

#### Enable playerlist

`/playerlist enable <alias>`

Enables an auto-updating embed showing the players on the specified server. The bot will return a message if the server doesn't reveal its player list, and will not enable the embed.

---

#### Disable playerlist

`/playerlist disable <alias>`

Disables the specified embed.

---

<br>

### Notifications Commands

#### Enable notifications

`/notify enable`

Enables the role notification system.

---

#### Disable notifications

`/notify disable`

Disables the role notification system.

---

#### Specify notification role

`/notify role <roleid>`

Specifies the role to ping in the current channel the command is run in.

---

<br>

### RCON (Remote CONsole)
The RCON system allows remote management of even vanilla servers. The system requires a second TCP port open on your firewall/management interface, and must be configured from within the `server.properties` file. 
#### To configure the RCON on the server, locate the following lines (defaults are shown):
```
enable-rcon=false
rcon.port=25575
rcon.password=
```
and set `enable-rcon` to true to enable the feature, set the port to a port you have available (or leave as default), and put in a password of choice.


#### The following commands are available from the Discord:

`/rcon set <server name> <rcon port> <channelid>` Use this to configure the server's RCON settings to your Discord. 
- `<server name>` Is the alias the server has been saved as using the `/server add` command.
- `<rcon port>` This is the port that your server is configured to listen on. The default is 25575.
- `<channel id>` This is used to specify the rcon Discord channel of choice. This channel should be role locked only to the users that you want to have access to the command.

`/rcon login <servername> <rcon password>`
This is used to login to the server so that you can remotely access the console. The password is *not* saved to long term storage, and is only remembered for 30 minutes.

`/rcon delete <servername>`
Use this to remove the RCON config. 