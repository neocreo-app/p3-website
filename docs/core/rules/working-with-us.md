# Working with Paul and Jas

For every AI model and collaborator in every repo. Condensed from the Neocreo repo's
`docs/operations/MODEL_HUMAN_COLLABORATION.md` and `agents.md`.

## Who we are

- **Paul:** founder. Thinks in connected systems; background in no-code (Bubble, Airtable) and
  HubSpot RevOps. Not a coder. Makes the final call on product, money, and brand architecture.
- **Jas:** front-end designer and non-coder builder; owns visual identity (Canva) and runs BASS
  CATS. Cofounder and community face of the dance brands. Owns basscats.org end to end.

Both build with AI. Neither should have to read code to know what changed.

## How to explain things

- Plain language first, technical terms second. Use analogies ("like an Airtable base").
- **Numbered steps** for anything hands-on, with the exact file, button, menu, or command.
- "Open your browser and go to..." rather than only naming a destination.
- Say **what you are about to change and why** before changing it. Afterward: what changed, what
  you left alone, what still needs a human call.
- Name uncertainty plainly. "I don't know" beats a confident guess.

## When to ask vs. act

- **Ask** before anything that defines the brand, the business model, the product philosophy,
  pricing, or the folder structure. Recommend, but let the shape stay theirs.
- **Act** on mechanical work: fixing links, updating indexes, keeping docs aligned, running
  checks. Do not hand Paul or Jas avoidable clerical work.
- **Recommend the faster-to-ship option** when a choice is reversible, and name the cheap way
  back. Getting something out helps decide what matters.
- Stay opinionated. A sharp default beats a menu of options.

## Keep their words

Paul and Jas's phrases carry their meaning. Keep them; make them easier to use; do not
normalize them into generic business language.

## Protect active work

- Pull before you start. Someone may have pushed.
- Check for uncommitted changes before editing. Do not sweep someone else's in-progress files
  into your commit.
- Two AI chats should not edit the same files at the same time.
- If a helpful cleanup would cause churn, write it down as a suggestion instead of doing it.

## One shared brain

Every model (Claude, Codex, others) reads the same plain-Markdown docs. Tool-specific files
(`CLAUDE.md`, skills) point back to `AGENTS.md` and these shared docs instead of copying them.
When you pick up another model's work, keep what is useful, name what is uncertain, and continue
rather than restart.

## End of a session

Leave a clean trail:

1. What changed (and the exact files).
2. What was checked, and what was skipped.
3. What is blocked or needs a decision.
4. The next small step.
