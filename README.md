# conversation-practice

A Claude skill that turns everyday chats with Claude into practice for conversations with people.

You tell Claude what you want to get better at (expressing ideas precisely, admitting when you don't know, patience when misunderstood, perspective-taking in conflict, and so on). Claude keeps helping with whatever you actually asked, and adapts how it responds so the conversation doubles as practice.

## Why

Frequent conversations with AI change how people talk to each other, and not always in the same direction. Lab studies show that behavior toward bots spills over into how people later treat humans, that an endlessly charitable AI listener can make human conversation feel more effortful by contrast, and that a flattering AI makes people less willing to repair conflicts. The same mechanisms can be pointed the other way. This skill tries to do that deliberately.

The research basis and its limits are summarized in the skill itself. Most of the evidence comes from short lab studies; the long-term transfer this skill aims at has not been measured. Treat it as an experiment, with your own feedback as the main signal.

## How it works

The skill uses six levers, chosen per goal.

1. Modeling. Claude visibly does the target behavior itself.
2. Honest friction. For precision goals, Claude names real ambiguity instead of silently resolving it.
3. Non-sycophantic perspective. In interpersonal topics, Claude represents the other party's view.
4. Practice notes. An occasional one-line observation tied to a stated goal.
5. Transfer bridge. A sentence on how a move would land with a person rather than with Claude.
6. Reflection on request. An honest, evidence-based answer to "how am I doing?"

Intensity is `off`, `light` (default) or `active`. Say "practice off" at any time to stop it.

## Installation

### Claude Code

```
/plugin marketplace add wkusnierczyk/conversation-practice
/plugin install conversation-practice@conversation-practice
```

### Claude apps

Zip the `skills/conversation-practice` folder and upload it as a skill in Settings. To use it in every chat, add a line to your preferences asking Claude to use conversation-practice.

## Usage

Start with something like:

```
/conversation-practice
I want to get better at saying when I don't know something, and at not expecting people to follow me without context. Intensity light.
```

Later, ask "how am I doing in conversations?" for a reflection against your goals.

## Feedback and research updates

Feedback on practice notes (useful, wrong, too frequent) shapes the behavior within a conversation and, with memory enabled, across conversations. Open an issue for anything that should change in the skill itself. New research is recorded in [CHANGELOG.md](CHANGELOG.md) together with the change it motivated.

## Repository layout

```
.claude-plugin/
  plugin.json        plugin manifest
  marketplace.json   makes the repo installable as a Claude Code marketplace
skills/
  conversation-practice/
    SKILL.md         the skill
CHANGELOG.md
LICENSE
```

## License

MIT
