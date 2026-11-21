# Repository instructions

## Scope

This repository distributes the `clean-vibes` skill.
The canonical instructions are in `skills/clean-vibes/SKILL.md`.
Read the current skill before changing behavior.
Keep edits limited to the requested outcome.

The skill adds warmth when an agent chats with the operator who runs it.
It is opt-in.
It pairs with Clean Comms and does not change Clean Comms.
Keep this skill out of professional and outside writing.
Never tell the agent to use emoji in a message to another agent.

The emoji the agent may send are a closed set.
Each one has one meaning, for inline emoji and for reactions.
A change to that set must update the skill and the README together.

Short messages stay the default.
Extra detail belongs in the skill only when a rule needs it to be usable.

## Documentation

- Keep the skill folder and the frontmatter `name` as `clean-vibes`.
- Update the README when install steps or skill behavior change.
- Preserve the MIT license.
- Do not add `CHANGELOG.md`.
- The release workflow is `.github/workflows/release.yml`, copied from clean-comms.
- Do not add a plugin manifest or a sync script unless asked.

## Git and delivery

- Create short-lived branches from `dev`.
- Open pull requests against `dev`.
- Do not push directly to `dev` or `main` for routine changes.
- Promote `dev` to `main` only when authorized.
- Use Clean Commit messages: `<emoji> <type>: <description>`.
  Use lowercase, present-tense descriptions. Do not add a final period.
  Common pairs are `📖 docs`, `📦 new`, `🔧 update`, `⚙️ setup`, and `🧪 test`.

## Validation

For skill or documentation changes, inspect the diff and run `git diff --check`.
Check that relative Markdown links resolve.
Check that the frontmatter `name` matches the skill folder.
Check that the skill still limits sent emoji to the closed set.
