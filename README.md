# The Boardroom

> Eighteen advisors, a small team of the people who actually build the thing you are talking to, and one tidy way of carrying them all around. Bring your own tea.

## The Point Of The Exercise

In any given week a person is required to make a number of decisions, of which roughly three genuinely matter and the remaining several hundred merely feel as though they do. The difficulty has never been making decisions, at which humans are enthusiastically prolific, but rather telling the important ones apart from the rest and then working out what to do about them, ideally before the tea goes cold.

The Boardroom is a modest attempt to help with exactly that. It is a pair of Agent Skills for Claude that summon a room full of strongly opinionated advisors. You bring an idea, a plan, a deal, a repo, or a vague sense of unease, and they engage with it, locate the flaw you had been carefully not looking at, and then argue amongst themselves about the correct way to fix it.

The advisors are not real, in the narrow and frankly overrated sense that you cannot buy any of them a drink. They are real in the far more useful sense that they will reliably tell you things you needed to hear and would, on balance, have preferred not to.

There are two rooms. You are welcome in both.

## The Advisory Board

The Advisory Board is a panel of eighteen thinkers assembled, at no small expense of reading, from the public record of people who are unusually good at one particular way of seeing the world.

There is a value-and-temperament corner (Munger, Buffett) and a build-it-impossibly-fast corner (Musk, Bezos, Jensen) who do not always get along, which is the point. There are the persuaders (Voss, Cialdini), the marketer who will tell you to give before you ask (Gary V), and the Stoic who will tell you the obstacle was the way all along (Holiday). There are the people who think about thinking (Deutsch, Sagan, Naval), the people who think about machines that think (Dario, Karpathy), the contrarian who wants to know your secret (Thiel), and the producer who mostly wants you to take things away until only the good part is left (Rubin).

There is also Douglas Adams, who sits on the board chiefly to point out, at the cosmically appropriate moment, that the thing everyone is panicking about is both smaller and funnier than it appears. He has been told that a README has been written in his style. He has elected not to comment, which from him counts as a rave review.

You can summon one of them, a pair of them, a themed panel, or the entire board at once. When you do the latter you should expect disagreement, because a board that agrees with everything is not a board, it is a mirror, and you already own one of those.

Use the Advisory Board for strategy, big decisions, creative blocks, negotiations, persuasion, philosophy, and the occasional existential wobble about whether any of it matters. (It does, a bit, in the way that most things do.)

## The Code Team

The Code Team is a smaller, more technical room. Its members are the people who actually build Claude Code, plus Matt Pocock, who has been wired in to hold the chair marked "software engineering fundamentals and TypeScript," on the grounds that someone in the room should be quietly insisting the codebase remain comprehensible to a human after the agents have been through it.

This is the room to walk into when the question involves real code: architecture decisions, CLAUDE.md philosophy, hooks and plugins, parallel agent workflows, testing, and the eternal and important matter of working out whether the slop your agent just produced is the fault of the prompt or the fault of the codebase. They will engage with your reasoning first, then find the gap, then tell you what to do about it, which is the correct order for these things.

It is worth saying plainly, because the name suggests otherwise: the Code Team is not confined to Claude Code. The room is named after who the advisors are, not where they are allowed to stand. They will happily look over your engineering thinking in chat or in Cowork as well. Two further advisors (Linus Torvalds and Yann LeCun) are also in the box but are currently sitting quietly in the corner, unlisted in the panel, available to be brought into the conversation whenever you decide they have something to add.

## How To Actually Use It

This is the part where you, regrettably, have to do something. It is brief.

The important fact, the one that saves you a great deal of confusion later, is this: a Skill is the portable unit, an open standard, the same folder of instructions running in every Claude surface. You are not maintaining two versions of anything. You have one set of advisors and two ways of wrapping them, because Claude Code and the chat apps disagree, politely, about how they like to be handed a Skill.

### In Claude Code

Claude Code takes the whole thing as a single plugin. Point a session at the folder to try it out:

```bash
claude --plugin-dir ./boardroom
```

Or drop it into your skills directory so it loads every session without being asked twice:

```bash
cp -r boardroom ~/.claude/skills/boardroom
```

Inside Claude Code the skills are namespaced, so they appear as `boardroom:advisory-board` and `boardroom:code-team`. Run `/reload-plugins` if you have been editing.

### In Claude chat and Claude Cowork

The chat apps take Skills one at a time rather than as a plugin, so the two boards are also provided as standalone Skill zips. In claude.ai go to Customize > Skills, and upload each one separately:

- `advisory-board-skill.zip`
- `code-team-skill.zip`

Claude Cowork lives in the same ecosystem and accepts Skills the same way, so load them there exactly as you would in chat. Custom Skills require code execution to be enabled in settings, and are available on the Pro, Max, Team, and Enterprise plans.

That is genuinely all of it. One plugin install for Code, two Skill uploads for chat and Cowork, the same advisors behind all three.

## What's In The Box

```
boardroom/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    ├── advisory-board/
    │   ├── SKILL.md
    │   ├── references/
    │   │   ├── pairings.md
    │   │   └── sub_advisory_panels.pdf
    │   └── assets/personas/        (18 advisors)
    └── code-team/
        ├── SKILL.md
        └── assets/personas/        (the build team, Matt, and two in reserve)
```

The prebuilt zips (`boardroom-plugin.zip`, `advisory-board-skill.zip`, `code-team-skill.zip`) are the same content packaged for the surfaces above, so that nobody has to compress anything by hand and get the folder structure subtly, maddeningly wrong.

## Summoning Phrases

You do not strictly need these, because the boards will turn up on their own when the conversation calls for them, but they are pleasant to know:

- "Ask the board" brings in a relevant handful.
- "What would [name] think" calls a single advisor.
- "Channel [name]" keeps that advisor on for a longer conversation.
- "Ask the code team" assembles the technical room.
- Naming two advisors pits them against each other, which is where the useful sparks tend to come from.

## A Note On The People In Here

Everyone in these rooms is an affectionate reconstruction, assembled from public talks, books, interviews, and writing, in order to channel a way of thinking. They are not the actual individuals, they do not speak for the actual individuals, and the actual individuals are entirely unaware that they have been seated around a table and asked their opinion of your refinance strategy. Treat their advice as a useful prompt for your own judgement rather than as a verdict from on high. The judgement, in the end, stays with you. That part was never going to be outsourced.

## The Long And Short Of It

If you take nothing else from this document, take this: the advisors exist to make you think more clearly, not to think for you. Use them, argue with them, and ignore them when they are wrong. You will be fine.
