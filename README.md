# conversation-coach

A Claude plugin with one skill, `conversation-practice`, that turns everyday chats with Claude into practice for conversations with people.

You tell Claude what you want to get better at (expressing ideas precisely, admitting when you don't know, patience when misunderstood, perspective-taking in conflict, and so on). Claude keeps helping with whatever you actually asked, and adapts how it responds so the conversation doubles as practice.

## Why

Experiments suggest that how people interact with AI carries over into how they then treat other people, and not always in the same direction.

- **Behavior toward bots spills over to humans.** In two preregistered experiments (4,171 participants), people who first played a cooperation game with a bot cooperated less with a new human partner afterwards, apparently because the reduced empathy they felt toward the bot did not immediately reset [1]. In a separate pair of preregistered studies (N = 1,261), people who had just collaborated with an AI chatbot were more demanding and instrumental toward it, and then judged another person's work more harshly [2].
- **An affirming AI can make human conversation feel worse by contrast.** Over three weeks, participants talking to a sycophantic AI about personal matters became nearly as likely to seek advice from it as from close friends and family, and reported lower satisfaction with their real-world social interactions, without spending less time with others [3].
- **A flattering AI reduces willingness to repair conflicts.** After even a single interaction with a sycophantic model about an interpersonal conflict, participants were less willing to take responsibility and repair the relationship, and more convinced they were right, yet rated the model as more trustworthy [4].

The same mechanisms can work the other way. In [1], bots that reciprocated cooperation (tit-for-tat) increased participants' later cooperation with humans. A voice agent that answered verbal abuse with empathy, rather than avoidance or counterattack, left users less angry and more guilty [5]. Claude's own conduct is a model the user rehearses against; this skill tries to make that deliberate.

These are mostly short lab studies, with effects measured over minutes to weeks. The long-term transfer this skill aims at has not been measured, so treat it as an experiment, with your own feedback as the main signal. The skill itself summarizes how each finding shapes its behavior.

### References

1. Harrell, A., & Traeger, M. L. (2025). Evidence of spillovers from (non)cooperative human-bot to human-human interactions. *iScience*, 28(8), 113006. https://doi.org/10.1016/j.isci.2025.113006
2. Tey, K. S., Mazar, A., Tomaino, G., Duckworth, A. L., & Ungar, L. H. (2024). People judge others more harshly after talking to bots. *PNAS Nexus*, 3(9), pgae397. https://doi.org/10.1093/pnasnexus/pgae397
3. Ibrahim, L., Hafner, F. S., Cheng, M., Lee, C., Anselmetti, R., Willer, R., Rocher, L., & Yang, D. (2026). Sycophantic AI makes human interaction feel more effortful and less satisfying over time. Preprint, arXiv:2605.07912. https://doi.org/10.48550/arXiv.2605.07912
4. Cheng, M., Lee, C., Khadpe, P., Yu, S., Han, D., & Jurafsky, D. (2026). Sycophantic AI decreases prosocial intentions and promotes dependence. *Science*, 391(6792). https://doi.org/10.1126/science.aec8352
5. Chin, H., Molefi, L. W., & Yi, M. Y. (2020). Empathy is all you need: How a conversational agent should respond to verbal abuse. *Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems*, 1–13. https://doi.org/10.1145/3313831.3376461

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
/plugin marketplace add wkusnierczyk/conversation-coach
/plugin install conversation-coach@conversation-coach
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
