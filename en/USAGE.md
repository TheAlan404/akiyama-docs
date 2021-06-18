# Akiyama Docs

[Back](./INDEX.md)

Usage
-----

#### Note

In commands, the required fields will begin and end
with the `<` and `>`, meanwhile the optional fields
will be shown with `[` and `]`.


## OOC Messages

OOC messages are Out Of Character messages, generally
used in roleplays to speak out of your character,
for example telling your friend you are AFK.

Some examples of OOC messages include:
- `((no you cant do that`
- `//bro stop`
- `im afk))`

Sometimes the roleplay channel may be filled with
OOC messages. To help you with this, 
Akiyama has two little commands for you.

---

> <a name="cmd_clearooc"></a> `.clearooc`

**Aliases:** `.cooc`

Clears OOC messages in the channel. If you dont have
the permissions to delete others' messages, Akiyama
will only delete your own OOC messages.

---

> <a name="cmd_autoclearooc"></a> `.autoclearooc [duration]`

**Requires:** administrator permissions

This is a setting, when set, Akiyama will delete any OOC message
after *duration* seconds.

Also, if an OOC message has `!` as the message's *3rd* character,
 (ex: `((! hi` ) Akiyama will not automatically delete it.
This is useful when the other person is taking too long to respond.

To turn off this feature, you can type `.autoclearooc off`

## Area Commands

Areas are locked channels that are connected in the database of Akiyama.
Areas can be used to:
- Make Among Us type rooms
- Add housing to your roleplay server
- Create SCP-type rooms
and many more. Its only limited by your imagination.

How it works is every area (a channel in this case) is locked.
Members use a command to move between two areas, 
which gives access to where they are going and removes access from where they were before.

### User Commands

---

> <a name="cmd_move"></a> `.move`

**Requires:** none

Move to another area. Akiyama gives a prompt, asks you where to go.
Type the number to select and go to that area.

![Move Command Usage by takipsizad](https://ta.is-inside.me/nTEPxm27.gif)

---

> <a name="cmd_connections"></a> `.connections`

**Requires:** none

**Aliases:** `.conns`

Sends a list of the connections this area has.



### Admin Commands

---

> <a name="cmd_forcemove"></a> `.forcemove <@user>`

**Requires:** "move member" permissions

Forcefully moves a user from one area to another.
The same prompt for `.move` is given, but after selection
the mentioned user is moved without checking for any requirements.

For example, use this command to move your prisoners into their jail cell.

---

> <a name="cmd_create"></a> `.create [category id] <name>`

**Requires:** administrator permissions

Creates a channel and saves it as an area.
Creates the channel in the same category the command has runned in.

*Examples:*
- `.create hotel-room-6`
- `.create 852916054531637289 long-corridor`

---

> <a name="cmd_bind"></a> `.bind [#channel(s)]`

**Requires:** administrator permissions

Saves a channel as an area, locks it if it is not locked.
If channel is not given, saves the current channel.
Accepts multiple channels

*Examples:*
- `.bind`
- `.bind #security-office`
- `.bind #hotel-room-2 #hotel-room-7 #elevator`

---

> <a name="cmd_bindcategory"></a> `.bindcategory <category id>`

**Requires:** administrator permissions

Binds a whole category/all the channels inside of it.

---

> <a name="cmd_label"></a> `.label`

**Requires:** administrator permissions

**Aliases:** `.setlabel`

Sets a label for the area.
Labels are nicknames that override the name in `.move` or `.connections`

---

> `.connect <#channel1> <#channel2>`

**Requires:** administrator permissions

Connects two areas, so the users can use `.move` to move between the two areas.

---

> `.deconnect <#channel1> <#channel2>`

**Requires:** administrator permissions

Removes the connection.

---

#### <a name="Requirements"></a> Requirements

In Akiyama, you can have requirements in area connections.
Requirements basically check for certain conditions, 
for example if the user has a role or not.

Requirements can have a data associated with it.

<a name="reqtypes"></a> **Requirement Types**
- `item_has`
    data is an item id
    checks if the user has the item in their inventory
- `item_nothas`
    data is an item id
    checks if the user *doesnt have* the item in their inventory
- `roles_has`
    data is a role id
    checks if the user has the role
- `role_nothas`
    data is a role id
    checks if the user *doesnt have* the role
There are more requirements, but they are WIP.

Okay, now back to the commands.

---

> `.addrequirement <connection idx.> <req. type> <req. data>`

**Requires:** administrator permissions

**Aliases:** `.addreq`

Adds a requirement to a connection. This can be used to "lock" an area to certain users.
For example, a hotel room that requires a keycard.

✨ **Editors Note!:** This looks very complicated, but trust me, its easy.
- Connection index is the number that you type when you use `.move`
- Req. type is the requirement type, for example `item_has`
- Req. data is the requirement's data.
  For example, if the requirement is `item_has` then it is the item's id.
  All the types and what their data is [can be found here](#reqtypes)

*Examples:*
- `.addreq 1 item_has ZMYSBI`

   add a requirement to the first connection,
   that checks if the user has the item with the ID 'ZMYSBI'

- `.addreq 1 role_has 850810225933025320`

   add a requirement that checks for the role


---

> `.removerequirement <connection index> <requirement index>`

**Requires:** administrator permissions

**Aliases:** `.remreq`

Removes a requirement. The requirement index is listed in the `.connections` command.

*Examples:*
- `.remreq 1 1`
- `.remreq 2 1`

---

## Item Management


TODO!!! -dennis

