# Akiyama Docs

[Back](./INDEX.md)

⚠️ **DOCS ARE IN PROGRESS!** ⚠️

Usage
-----

## <a name="settings"></a> Settings

To modify the server-specific settings, use the `/settings` command.
**Requirements:**
- Permission: Manage Server

---

## <a name="ooc"></a> OOC Messages

OOC messages are Out Of Character messages, generally
used in roleplays to speak out of your character,
for example telling your friend you are AFK.

Some examples of OOC messages include:
- `((no you cant do that`
- `//bro stop`
- `im afk))`

Sometimes the roleplay channel may be filled with
OOC messages. Akiyama can help!

---

> <a name="cmd_clearooc"></a> `/clearooc`

Clears OOC messages in the channel. If you dont have
the permissions to delete others' messages, Akiyama
will only delete your own OOC messages.

---

> <a name="cmd_autoclearooc"></a> `/autoclearooc [duration]`

**Requires:**
- Permission: Manage Server

This is a setting, when set, Akiyama will delete any OOC message after *duration* seconds.

ℹ️ Also, if an OOC message has `!` as the message's *3rd* character,
(ex: `((! hi` ) Akiyama will not automatically delete it.
This is useful when the other person is taking too long to respond.

ℹ️ To turn off this feature, you can set the `duration` to `0` (zero).

ℹ️ The maximum duration is 10 minutes, but this might change in the future if users want (drop by our server!)

---

## <a name="area"></a> Area Commands

Areas are locked channels that are connected in the database of Akiyama.
Areas can be used to:
- Make Among Us type rooms
- Add housing to your roleplay server
- Create SCP-type rooms
and many more. Its only limited by your imagination.

ℹ️ How it works is every area (a channel in this case) is locked.
Members use a command to move between two areas, 
which gives access to where they are going and removes access from where they were before.

This can be used to add an effect of realism.

### User Commands

> <a name="cmd_move"></a> `/move`

**Requires:**
- Must be run in an area

Move to another area. Akiyama gives a prompt, asks you where to go.



> <a name="cmd_area_edit"></a> `/area edit`

**Requires:**
- Must be run in an area
- Permission: Manage Channels

Use this command to edit the current area.
