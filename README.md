# The client room skill

Lock 12 Claudes in a room until they find you a paying client. Every Claude gets one job, they vote in secret, and the door only opens when they agree. You get your top 3 clients, the proof for each one, and the first message to send.

Made by **Alex Chen** ([@nocodealex](https://instagram.com/nocodealex)), an AI creator who builds free Claude Code skills. More at [chen.media](https://chen.media).

## How it works

`/client-room` asks what you sell, where, and your usual price. Then 12 Claude sub-agents hunt at the same time, three per method:

| Method | What it looks for |
|---|---|
| Bad Google reviews | local businesses whose reviews complain about what you fix, or whose website looks old |
| Job posts | posts asking for work you could do freelance |
| New businesses | places that opened this month and need everything |
| Hiring posts | companies hiring for a role you could fill as a contractor |

Every lead needs a source link (the review, the post, the announcement), or it is thrown out. Then the same 12 vote in secret, each alone, at most 5 yes votes each. A lead needs **7 of 12** to get out of the room. The top 3 come out with their proof and a short first message that quotes the exact problem.

## Install

Paste this into Claude Code:

```
https://github.com/alexyc9381/client-room-skill
Install this skill, then confirm /client-room works.
```

Or as a plugin:

```
/plugin marketplace add alexyc9381/client-room-skill
/plugin install client-room-skill@client-room-skill
```

Or copy the folder yourself:

```bash
git clone https://github.com/alexyc9381/client-room-skill
cp -r client-room-skill/skills/client-room ~/.claude/skills/
```

Needs Claude Code with web search (it spawns sub-agents) and Python 3.8+. Nothing to pip install, no API keys.

## Use it

```
/client-room
/client-room websites for restaurants in Austin, about $1,500
```

You get `.client-room/REPORT.md`: your top clients, the proof, why the room voted for them, and the first message to send.

## Good to know

- 24 sub-agents per run (12 hunt, 12 vote), so it uses a fair part of your Claude plan.
- It only uses public pages it can link to. It never sends anything: you send the messages.
- Check each lead before you reach out; a review or post can be old or already handled.
- It is not made by Anthropic.

Run the tests with:

```bash
python3 -m unittest discover -s tests
```
