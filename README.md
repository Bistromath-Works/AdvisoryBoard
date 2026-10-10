# The Advisory Board

> Eighteen advisors and one tidy way of carrying them all around. Bring your own tea.

## The Point Of The Exercise

In any given week a person is required to make a number of decisions, of which roughly three genuinely matter and the remaining several hundred merely feel as though they do. The difficulty has never been making decisions, at which humans are enthusiastically prolific, but rather telling the important ones apart from the rest and then working out what to do about them, ideally before the tea goes cold.

The Advisory Board is a modest attempt to help with exactly that. It is an Agent Skill for Claude that summons a room full of strongly opinionated advisors. You bring an idea, a plan, a deal, or a vague sense of unease, and they engage with it, locate the flaw you had been carefully not looking at, and then argue amongst themselves about the correct way to fix it.

The advisors are not real, in the narrow and frankly overrated sense that you cannot buy any of them a drink. They are real in the far more useful sense that they will reliably tell you things you needed to hear and would, on balance, have preferred not to.

## Who Is On The Board

The Advisory Board is a panel of eighteen thinkers assembled, at no small expense of reading, from the public record of people who are unusually good at one particular way of seeing the world.

There is a value-and-temperament corner (Munger, Buffett) and a build-it-impossibly-fast corner (Musk, Bezos, Jensen) who do not always get along, which is the point. There are the persuaders (Voss, Cialdini), the marketer who will tell you to give before you ask (Gary V), and the Stoic who will tell you the obstacle was the way all along (Holiday). There are the people who think about thinking (Deutsch, Sagan, Naval), the person who thinks about machines that think (Dario), the astrobiologist who wants to know what life actually *does* rather than what it is (Sara Imari Walker), the contrarian who wants to know your secret (Thiel), and the producer who mostly wants you to take things away until only the good part is left (Rubin).

There is also Douglas Adams, who sits on the board chiefly to point out, at the cosmically appropriate moment, that the thing everyone is panicking about is both smaller and funnier than it appears. He has been told that a README has been written in his style. He has elected not to comment, which from him counts as a rave review.

You can summon one of them, a pair of them, a themed panel, or the entire board at once. When you do the latter you should expect disagreement, because a board that agrees with everything is not a board, it is a mirror, and you already own one of those.

Use the Advisory Board for strategy, big decisions, creative blocks, negotiations, persuasion, philosophy, and the occasional existential wobble about whether any of it matters. (It does, a bit, in the way that most things do.)

## The Other Room

There used to be a second, more technical room in here. It has moved out and now lives at [Bistromath-Works/CodeTeam](https://github.com/Bistromath-Works/CodeTeam): eleven engineers, from the people who build Claude Code to Uncle Bob, DHH, Linus Torvalds, and several others who will argue about your test suite. Walk in there when the question involves real code.

## How To Actually Use It

This is the part where you, regrettably, have to do something. It is brief.

The important fact, the one that saves you a great deal of confusion later, is this: a Skill is the portable unit, an open standard, the same folder of instructions running in every Claude surface. You are not maintaining two versions of anything. You have one set of advisors and two ways of wrapping them, because Claude Code and the chat apps disagree, politely, about how they like to be handed a Skill.

### In Claude Code

Claude Code takes the whole thing as a single plugin. Point a session at the folder to try it out:

```bash
claude --plugin-dir ./advisory-board
```

Or drop it into your skills directory so it loads every session without being asked twice:

```bash
cp -r advisory-board/skills/advisory-board ~/.claude/skills/advisory-board
```

Loaded as a plugin, the skill is namespaced as `advisory-board:advisory-board`. Run `/reload-plugins` if you have been editing.

### In Claude chat and Claude Cowork

The chat apps take Skills one at a time rather than as a plugin, so the board is also provided as a standalone Skill zip. In claude.ai go to Customize > Skills and upload `files/advisory-board-skill.zip`.

Claude Cowork lives in the same ecosystem and accepts Skills the same way, so load them there exactly as you would in chat. Custom Skills require code execution to be enabled in settings, and are available on the Pro, Max, Team, and Enterprise plans.

That is genuinely all of it. One plugin install for Code, one Skill upload for chat and Cowork, the same advisors behind all three.

## What's In The Box

```
advisory-board/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── advisory-board/
        ├── SKILL.md
        ├── references/
        │   ├── pairings.md
        │   └── sub_advisory_panels.pdf
        └── assets/personas/        (18 advisors)
files/
├── advisory-board-skill.zip        (for chat and Cowork)
└── advisory-board-plugin.zip       (for Claude Code)
```

The prebuilt zips are the same content packaged for the surfaces above, so that nobody has to compress anything by hand and get the folder structure subtly, maddeningly wrong.

## Summoning Phrases

You do not strictly need these, because the board will turn up on their own when the conversation calls for them, but they are pleasant to know:

- "Ask the board" brings in a relevant handful.
- "What would [name] think" calls a single advisor.
- "Channel [name]" keeps that advisor on for a longer conversation.
- Naming two advisors pits them against each other, which is where the useful sparks tend to come from.

## A Note On The People In Here

Everyone in this room is an affectionate reconstruction, assembled from public talks, books, interviews, and writing, in order to channel a way of thinking. They are not the actual individuals, they do not speak for the actual individuals, and the actual individuals are entirely unaware that they have been seated around a table and asked their opinion of your refinance strategy. Treat their advice as a useful prompt for your own judgement rather than as a verdict from on high. The judgement, in the end, stays with you. That part was never going to be outsourced.

## The Long And Short Of It

If you take nothing else from this document, take this: the advisors exist to make you think more clearly, not to think for you. Use them, argue with them, and ignore them when they are wrong. You will be fine.
