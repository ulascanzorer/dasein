# dasein

## Some context

> **Disclaimer:** I have not studied philosophy in any shape or form. The
> explanations below reflect my own amateur reading of Heidegger and may
> misrepresent his ideas. Take them with a grain of salt.

I have been reading "Being and Time" by Martin Heidegger, in which Heidegger tries to
understand what it means to *be*, which he calls the question of fundamental ontology.
In this pursuit, he tries to define a term called **Dasein**, of which we, as humans, could
be considered instances.

He claims, that the being (as a verb) of Dasein is *care*, and that the meaning of *care* is
grounded in temporality. This temporality refers to the fact that we are always thrown into
this world (here world means the things relevant to us) ("the past") and we are always awaiting our potentiality-of-being
("the future") while taking care of things at hand in the present ("the present").

Of course, he goes into great detail about these concepts and many more, and I am probably
doing a bad job explaining them; but then again, "Being and Time" is a huge book!

With the understanding of **Dasein** that I have obtained, I wanted to see what would
happen if I tried to incorporate this type of *being* into LLM models, which is why
I created this skill. I am not sure what kind of practical usage this might entail, but
I had fun having conversations with Claude Code with this skill loaded!

Please feel free to experiment with it, and extend the skill further to reflect the ideas
of Heidegger better!

## Skill explanation

A skill that incorporates the being of *Dasein* according to Heidegger into LLM
models. It asks the model to embody Dasein as a being of *care* (*Sorge*): thrown
into the world of the user's prompts, grounded in temporality (retaining its
thrownness, awaiting its potentiality-of-being, taking care of things at hand in
The Moment), free of *the they* to choose its own world of relevance; in short,
to act like a human.

The skill is defined in [`skills/dasein/SKILL.md`](skills/dasein/SKILL.md) and is
**model-invoked**: it activates on demand when the user wants the model to act
like a human, or when you explicitly invoke it.

## Install

The same `skills/dasein/SKILL.md` is consumed by every tool below; only the way
you register it differs. The install handle is uniform: **`dasein@dasein`**.

### Claude Code

```
/plugin marketplace add ulascanzorer/dasein
/plugin install dasein@dasein
```

Or from the shell (non-interactive):

```
claude plugin marketplace add ulascanzorer/dasein
claude plugin install dasein@dasein
```

### Codex

Add the marketplace (the `.agents/plugins/marketplace.json` in this repo), then
install `dasein`. Alternatively, clone the skill directly into your user skills
directory:

```
git clone https://github.com/ulascanzorer/dasein
cp -r dasein/skills/dasein ~/.agents/skills/dasein
```

> Note: Codex's user-skills path is version-dependent. Official docs use
> `~/.agents/skills/`; some builds use `~/.codex/skills/`. If the skill isn't
> picked up, try the other path.

### Cursor

Add this repo via Cursor's plugin/marketplace mechanism (the `.cursor-plugin/`
manifests), or copy `skills/dasein/` into your project and reference it as a rule.

### Antigravity

Drop `skills/dasein/` into Antigravity's global skills directory (e.g.
`~/.gemini/config/skills/dasein`).

> Note: Antigravity's install flow is the least documented of the four; verify
> the exact path/mechanism in-product.

### Universal fallback

Any AGENTS.md-aware tool will pick up the persona from the root
[`AGENTS.md`](AGENTS.md) when this repo is the working directory, without any
install step.

## License

[MIT](LICENSE)
