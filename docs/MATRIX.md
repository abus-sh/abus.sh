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

# Message Recovery (**strongly** recommended)

## Why This Matters (can be skipped)

Matrix is end-to-end encrypted, which means that only you and your intended recipients can read
your messages (there are several asterisks here, ask your resident cryptography nerd for nuance).
This works by encrypting your messages with a key. Only you and your intended recipients have the
key that can decrypt your messages. This is great for privacy and security, but has a major
drawback: what if you lose your key? This can happen for many reasons, such as hardware failure or
signing out. Because of *math*, this key can't be recovered if lost entirely. This would mean that
you couldn't read your old encrypted messages.

Matrix solves this by allowing users to enable account recovery. This takes your key and encrypts it
with a password/key that only you know. The encrypted key is stored on the Matrix server. If you
lose your key, you can ask the Matrix server for the encrypted key. So long as you know the backup
password/key, you can decrypt your key and everything is back to normal. Since the key on the server
is encrypted, this doesn't compromise the secrecy of your messages.

## How to Enable Message Recovery

These steps only apply to the Element client. Other clients may have a different process (or may not
support this process at all). 

1. Sign into Matrix. If you don't have Element installed, you can use the
[Element web client](https://app.element.io/).
2. Click on your profile picture in the top left corner. This will open a new menu.
3. Click on "All settings". This will open a new menu.
4. Click on the "Encryption" tab in the new menu.
5. Under the "Recovery" heading, click "Set up recovery". If you have already set up account
recovery, this will say "Change recovery key" instead.
6. Click "Continue".
7. Your recovery key will appear. **You must save this someplace safe.** If you lose this recovery
key, message recovery will be harder or impossible.
8. Click "Continue".
9. Enter your recovery key. This checks to make sure you saved it correctly.
10. Click "Finish set up".
11. You will return to the previous screen. If it succeeded, the button that said "Set up recovery"
should now say "Set up recovery".
