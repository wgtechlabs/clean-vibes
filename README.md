# Clean Vibes

![Clean Vibes banner — Warm chat with the operator](<https://ghrb.waren.build/render/banner?header=Clean+Vibes&subheader=Warm+chat+with+the+operator&bg=2C1B16-7A4034&color=FFFFFF&subheadercolor=F8E7D8&headerfont=DM+Sans&subheaderfont=Inter&support=true&watermarkpos=bottom-right>)
<!-- Created with GitHub Repo Banner by Waren Gonzaga: https://ghrb.waren.build -->

[![License: MIT](https://img.shields.io/badge/license-MIT-7A4034)](LICENSE)

**Clean Vibes** is an opt-in skill that adds warmth when an AI agent chats with the operator who runs it.

It is for anyone whose agent can load an Agent Skills folder. It pairs with [Clean Comms](https://github.com/wgtechlabs/clean-comms). It does not change Clean Comms. Clean Comms still keeps messages short. This skill only adds tone, and only in that private chat.

The skill stays off when the agent writes for professional or outside use. The operator's request does not turn it back on for that text. That includes emails, posts, docs, pull requests, commits, GitHub comments, client messages, and any other text a person outside this chat will read. It never uses emoji in a message to another agent.

[Skill rules](skills/clean-vibes/SKILL.md) · [Repository instructions](AGENTS.md)

## ✨ Features

- **Opt-in, and separate.** The agent uses it only for chat with the operator. It does not change Clean Comms.
- **A closed emoji set.** Five emoji only: 👍 ✅ 🎉 😂 ❤️. Each has one meaning, for an inline emoji and for a reaction.
- **Rare on purpose.** At most one emoji in a message, and not on every message. Most messages have none.
- **It reads emoji too.** The agent treats the operator's emoji as meaning, tone, or sarcasm, and asks when a wrong guess would change the next action.
- **Warm, and still short.** Contractions and matched energy, inside the length Clean Comms already sets.
- **Off for outside text.** Professional drafts and messages to other agents stay plain.

## 🚀 Getting Started

You need an agent host that loads a skill from a folder containing `SKILL.md`. This repository has no package to install and no plugin manifest, so there is no marketplace command.

1. Copy `skills/clean-vibes/` into the skills directory your host already uses.
2. Start a new session so the host loads the skill. Its name is `clean-vibes`.

Load [Clean Comms](https://github.com/wgtechlabs/clean-comms) beside it when you also want the short-message rules. Clean Vibes does not replace those rules.

### Codex

Codex discovers project skills from `.agents/skills/`. Copy `skills/clean-vibes/` to `.agents/skills/clean-vibes/` in your project, then start a new Codex session. The included `SKILL.md` uses the required `name` and `description` metadata. See [OpenAI's Codex skill guidance](https://developers.openai.com/blog/skills-agents-sdk).

Ask for a small status update in the same chat. The first useful result is still one or two lines. An emoji appears only when one rule in the skill fits.

## 📖 Usage

After the skill is loaded, a normal update stays short and usually has no emoji.

The operator says: "Rename the button."

```text
Button renamed. Tests passed.
```

The operator says: "Thanks for catching that."

```text
Glad that caught it. ❤️
```

That second sample is thanks, so ❤️ fits. The first sample is a routine result, so it has no emoji.

The agent sends emoji only from this set. The same rule covers an inline emoji and a reaction. Use at most one in a message, and not on every message. Most messages have none. Do not stack emoji, and do not use one as decoration. An inline emoji does not replace the sentence.

A reaction can be the whole reply when its meaning is the one in the table. A reaction counts as the one emoji for that message. If the agent reacts, it does not also put an emoji in the text. If the host has no reactions, the same emoji may appear once in the text.

Hold back when the operator is frustrated, the topic is serious, or the message is a failure report. Serious includes an outage, a loss, a conflict, money, health, and security. If the agent used an emoji in the last message or two, it skips the next one.

| Emoji | Meaning | Use it when | Do not use it when |
| --- | --- | --- | --- |
| 👍 | OK or agreed | You agree, or you confirm a choice they already made. | You are unsure, they are upset, or you are about to disagree. |
| ✅ | A small task is done | A small task in this chat is finished, and you checked it. | The result failed, it is partial, or it is big news. |
| 🎉 | Good news | The news is something they would actually celebrate. | The update is routine, mixed, or bad nearby. A small finished task is ✅, not this. |
| 😂 | Something is actually funny | They made a real joke, or the moment is genuinely funny, and the mood is light. | You are only being polite, you are not sure they were joking, or the topic is serious. |
| ❤️ | Thanks | You thank them for help, a correction, or a kindness. | It would be a default sign-off, or they did not just help you. |

### How the agent reads emoji

The agent reads the emoji the operator sends. It can carry the meaning, the tone, or the sarcasm. A reaction from the operator is a reply.

- 👍 means approval. If it answers a proposal, the agent goes ahead.
- 😅 means mild awkwardness, a small apology, or "this is slightly painful". It is not a big laugh, and it is not a crisis.
- 💀 means "very funny" in a light chat. It does not mean death. The agent does not treat it as an emergency when the mood is a joke.
- ❤️ means thanks or warmth.
- 😂 means they find it funny.
- 🙃 can mean sarcasm, or "this is fine" when it is not.

Words and emoji can disagree. When they do, the emoji often carries the tone. A cheerful sentence with 💀 or 🙃 may be a joke. The agent does not take the cheerful words at face value until the tone is clear.

The agent does not explain the operator's emoji back to them. It does not mirror an emoji they sent unless its own rule already allows that one emoji.

The agent asks one short question when the next action changes if it guesses wrong. It also asks when the emoji could mean harm and the topic is not clearly a joke, and when the message is only an emoji it cannot place. It does not ask when the meaning is clear enough to continue. A 👍 on the proposal it just made is clear. If 💀 sits next to news about a real person being hurt, the agent does not read it as a joke. It asks.

If the operator sends "ship it 😅" and the action is hard to undo, the agent asks: "Ship it, or hold?" If the change is small and local, the words say to ship, and 😅 is only mild awkwardness. The agent ships it.

### What stays plain

A draft for someone else has no emoji from this set. The chat around that draft can stay short and warm.

```text
Draft is ready.
```

A message to another agent has no emoji. It keeps the facts the next agent needs.

A repo convention that requires its own marks, such as a Clean Commit type emoji or a Clean README heading, is not this set. While the agent writes that document, this skill stays off.

## 📚 Documentation

- [clean-vibes skill](skills/clean-vibes/SKILL.md): the rules, the closed set, and good and bad examples.
- [Repository instructions](AGENTS.md): how to change this repository without widening its scope.
- [Clean Comms](https://github.com/wgtechlabs/clean-comms): the paired skill for short messages. It stays free of emoji.

GitHub Actions creates releases from `main` with [Release Build Flow Action](https://github.com/wgtechlabs/release-build-flow-action).

## 🛠️ Development

There is no application build and no automated test suite.

For a documentation or skill change:

1. Inspect the diff and run `git diff --check`.
2. Check that relative Markdown links resolve.
3. Check that the frontmatter `name` in `skills/clean-vibes/SKILL.md` is `clean-vibes`.

[AGENTS.md](AGENTS.md) is the full contributor checklist.

## 🤝 Contributing

Documentation and skill fixes are welcome. Read [AGENTS.md](AGENTS.md) before you open a pull request.

- Create a short-lived branch from `dev`.
- Open the pull request against `dev`.
- Do not push directly to `dev` or `main` for routine changes.
- Promote `dev` to `main` only when a maintainer has authorized it.
- Use [Clean Commit](https://github.com/wgtechlabs/clean-commit) messages: `<emoji> <type>: <description>`, in lowercase present tense, with no final period.

Keep the skill opt-in and separate from Clean Comms. Do not add a plugin manifest, a sync script, or a changelog unless a maintainer asks for it.

## 🐛 Issues & Support

Search [existing issues](https://github.com/wgtechlabs/clean-vibes/issues) before you open a [new issue](https://github.com/wgtechlabs/clean-vibes/issues/new).

For a skill question, include the behavior you expected and a short example of the message. Do not include credentials, private logs, or other secrets.

This repository has no separate security-reporting policy and no private support address.

## 📄 License

Clean Vibes is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 WG Technology Labs.

## 👥 Authors & Contributors

Created by **[Waren Gonzaga](https://github.com/warengonzaga)** under **[WG Technology Labs](https://github.com/wgtechlabs)**, with contributions from the [community](https://github.com/wgtechlabs/clean-vibes/graphs/contributors).
