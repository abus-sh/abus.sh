# How to Join matrix.abus.sh

This guide describes the process to join matrix.abus.sh using the Element web client. If you want to
join another instance or want to use a different client, you may need to adapt these instructions.

1. Get a registration token. If you don't have one, ask Abus for one.
2. Open the [Element web client](https://app.element.io/).
3. Click "Create Account".
4. Click the "Edit" button next to "matrix.org".
5. In the "Other homeserver" text box, type "matrix.abus.sh".
6. Enter a username and a password and click "Register".
7. Enter your registration token  and click "Continue".

Your full username is "@\<username\>:matrix.abus.sh". For example, if you entered "abus" as your
username, your username would be "@abus:matrix.abus.sh". You will need to give this to people for
them to invite you to conversations.

# Matrix Terminology

Conversations in Matrix take place in "rooms" (think Discord channels). These rooms may be organized
into "spaces" (kind of like Discord servers, but with differences). Rooms may be public or private
and may optionally be encrypted. Anyone can create a room and whoever creates the room has
administrator privileges in that room.

Direct messages take place in "chats", which are just rooms under a different name. Outside of a few
special circumstances, DMs are automatically end-to-end encrypted, so only people in the chat can
read the messages. Even the server administrators can't read your messages in encrypted chats.

All rooms live on a server (ex. matrix.abus.sh). Because Matrix is "federated", anyone can join a
room in any other server (that particpates in federation). You can create a room on matrix.abus.sh
and invite people from the matrix.org server. Similarly, you can join any room on any other
federated server.

# Matrix to Discord Bridge

A Matrix "bridge" allows communication between Matrix and some other platform (Discord, in this
case). It lets users on either communicate with each other. The bridge can apply to just one
channel/room, an entire Discord server ("guild", technically), or a user account.

The bridge used on this server operates in two modes, "relay" mode and "puppeting" mode. Relay mode
bridges servers and channels, while puppeting mode bridges entire accounts, with strings attached
(heh).

## Relay Mode

A Matrix admininstrator can bridge Discord servers or channels. When a server or channel is bridged,
equivalent rooms will exist in Matrix and messages on either end will be proxied to the other side
with no additional setup. However, the Matrix administrator must be involved in bridging new servers
or channels. Relaying also cannot bridge DMs. This is the easiest method for users to use since they
do not need to set anything up (or even have a Discord account).

## Puppeting Mode

As the name implies, this mode "puppets" (controls) a real Discord account. It can access all
servers you are a part of and can see your DMs. This method is much more powerful than relay mode
since it can access your entire account. However, this is a gray area of Discord's terms of service.
Your Discord account could theoretically be banned, however the author is not aware of any instances
of this happening at the time of writing (outside of some users who abused the system). More
information about puppeting your account can be found
[here](https://docs.mau.fi/bridges/go/discord/authentication.html). The author strongly recommends
*not* using the "token login" method.
