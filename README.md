# GSAP Creative Engineering

A reusable Agent Skill for designing, implementing, auditing, and visually validating distinctive, production-grade GSAP experiences in modern web applications.

This skill focuses on the **creative direction and engineering decisions around animation**: selecting the right interaction model for each section, building meaningful scroll-led experiences, creating visual depth, and keeping every layout responsive, accessible, performant, and readable.

> This skill complements [GreenSock's official GSAP AI skills](https://github.com/greensock/gsap-skills). Use the official skills for precise GSAP API and framework guidance; use this skill for art direction, interaction design, responsive behavior, project audits, and visual quality standards.

## What it covers

- Distinctive section concepts instead of repeating generic grids and fade-up effects.
- Scroll storytelling: pinned scenes, scrubbed text, horizontal galleries, vertical card stacks, parallax, progress navigation, and section transitions.
- 3D card previews, perspective, layered depth, lighting, and multi-layer box shadows.
- Kinetic typography, SplitText, SVG paths, MotionPath, Flip, Observer, and other GSAP tools when they serve a clear purpose.
- Responsive motion systems designed separately for mobile, tablet, laptop, and desktop.
- Full-content visibility: no clipped descriptions, hidden card details, cut-off controls, or inaccessible content.
- React/Next.js lifecycle safety, ScrollTrigger cleanup, SSR considerations, reduced-motion behavior, performance, and accessibility.
- Browser-based visual verification, screenshot review, and honest test reporting.
- Ongoing research against current official documentation and relevant design references before adopting unfamiliar or newly released features.

## Repository structure

```text
gsap-skill/
├── README.md
└── skills/
    └── gsap-creative-engineering/
        └── SKILL.md
```

The skill follows the open [Agent Skills format](https://agentskills.io/specification): a named skill directory containing a `SKILL.md` file with YAML frontmatter and instructions.

## Install

The examples below use this repository: [`maessamx/gsap-skill`](https://github.com/maessamx/gsap-skill).

### Google Antigravity

Run this from your target project:

```bash
npx skills add maessamx/gsap-skill --skill gsap-creative-engineering --agent antigravity
```

### Other supported agents

Change the agent name to the one you use. Examples:

```bash
# Claude Code
npx skills add maessamx/gsap-skill --skill gsap-creative-engineering --agent claude-code

# Cursor
npx skills add maessamx/gsap-skill --skill gsap-creative-engineering --agent cursor

# OpenAI Codex
npx skills add maessamx/gsap-skill --skill gsap-creative-engineering --agent codex
```

The Skills CLI installs project-level skills by default. Add `--global` when you want the skill available across projects, if the selected agent supports global installation. See the [Skills CLI reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) for current options and supported agent identifiers.

### Install GreenSock's official skills as well

For deeper API-specific guidance, install the official GSAP skill collection alongside this creative-engineering skill:

```bash
npx skills add greensock/gsap-skills --agent antigravity
```

The official skills and this repository serve complementary purposes: API correctness on one side, and design direction, responsive storytelling, and visual QA on the other.

## How to use it

After installation, ask your coding agent to use `gsap-creative-engineering` for website redesigns, GSAP animation systems, scroll interactions, horizontal/vertical card experiences, 3D previews, responsive motion, typography, SVG animation, transitions, parallax, and browser-based design QA.

For a full website audit, use a separate task prompt that explicitly tells the agent to read and follow this skill **before** inspecting or changing the project. The agent must inspect the real repository, installed GSAP version, existing integration, and available plugins before coding.

## Research references

The skill prioritizes current primary sources and treats inspiration examples as references to inspect—not code to copy blindly.

- [GSAP documentation](https://gsap.com/docs/v3/)
- [ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/)
- [SplitText](https://gsap.com/docs/v3/Plugins/SplitText/)
- [Flip](https://gsap.com/docs/v3/Plugins/Flip/)
- [Official GSAP AI skills](https://github.com/greensock/gsap-skills)
- [GSAPify animation library](https://gsapify.com/gsap-animations/#scroll-animations)
- [Scroll-driven image carousel reference](https://codepen.io/jh3y/pen/PovoorJ)

## Core principles

1. **Design first, animate with purpose.** Do not add effects simply to make a page look busy.
2. **Mobile is a first-class composition.** Do not shrink desktop layouts or force long pinned horizontal scenes onto narrow screens.
3. **Never hide real content.** Do not sacrifice descriptions, project details, links, or controls to fit an animation.
4. **Verify before claiming.** Run the project and inspect it in a browser whenever the environment permits.
5. **Check what is current.** Verify versions, plugin availability, API details, browser support, and release status before calling anything new or latest.

## License

No license is currently granted by this repository. Unless a license is added, all rights are reserved by the copyright holder. You may inspect the public repository, but redistribution, modification, or commercial reuse is not licensed by default.
