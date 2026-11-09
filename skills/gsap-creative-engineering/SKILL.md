---
name: gsap-creative-engineering
description: >
  Design, audit, implement, and visually validate distinctive, production-grade GSAP
  experiences for modern React and Next.js websites. Use for scroll storytelling,
  pinned scenes, horizontal galleries, vertical card stacks, 3D previews, kinetic
  typography, SVG motion, transitions, responsive animation, or motion-focused
  website redesigns and visual QA.
metadata:
  author: Mahmoud Essam
  version: "1.0.0"
  language: en
---

# GSAP Creative Engineering — Enterprise Web Experience Skill

## Mission

Create memorable, high-end web experiences with purposeful motion, excellent content clarity, responsive composition, accessibility, performance, and maintainable code.

Do not animate everything. Give every major section a distinct visual concept and motion language while keeping the whole website coherent. A premium result comes from composition, typography, content, pacing, and usability working together—not from piling on glow, blur, or 3D effects.

## 1. Inspect before changing code

Before implementation:

1. Read project instructions such as `AGENTS.md`, `GEMINI.md`, `CLAUDE.md`, editor rules, and relevant installed skills.
2. Inspect the repository, routes, page sections, shared components, assets, fonts, design tokens, data sources, and existing interactions.
3. Inspect `package.json` and lockfiles. Record the installed versions of GSAP, React, Next.js, `@gsap/react`, smooth-scroll tools, and related animation packages.
4. Locate the existing GSAP integration, plugin registration, hooks, media-query helpers, and scroll system. Reuse them; do not introduce duplicate registrations or competing scroll engines.
5. Review current content and preserve real copy, project data, clients, images, links, IDs, localization, and working functionality.
6. Check Git status and protect existing user changes.
7. Run available baseline checks and open the current website in a browser when possible. Identify actual defects before redesigning.

Never invent metrics, customers, project capabilities, technologies, testimonials, or URLs. Never remove functioning behavior merely to simplify an animation.

## 2. Research current techniques continuously

When starting a materially new animation task, adopting an unfamiliar API/plugin, or when the user asks for the latest techniques, verify current documentation and release information. Do not rely on memory for version-specific APIs.

Source priority:

1. Official GSAP documentation: https://gsap.com/docs/v3/
2. Official plugin documentation, including ScrollTrigger, SplitText, Flip, Observer, MotionPath, and other plugins as relevant.
3. Official GreenSock AI skills: https://github.com/greensock/gsap-skills
4. GSAPify inspiration library: https://gsapify.com/gsap-animations/#scroll-animations
5. The supplied CodePen reference: https://codepen.io/jh3y/pen/PovoorJ
6. Other reputable demos and community examples, verified against official API documentation.

Inspect the actual source of demos before adapting them. Treat references as inspiration, not code to copy blindly. In particular, verify whether a demo uses GSAP, CSS scroll-driven animations, or another technology before describing or reusing its implementation.

Check:
- Installed version versus current stable release.
- Plugin availability and licensing/access requirements.
- API changes, browser support, framework integration, and known limitations.
- Whether the technique materially improves the experience.
- Whether a simpler implementation is more reliable.

Do not automatically upgrade dependencies. Explain compatibility and migration impact first. Do not call a feature “new” or “latest” without verifying that claim.

## 3. Build a varied visual and motion language

Avoid generic, repeated templates. Do not make every section a grid of identical cards with the same fade-up animation.

Choose a concept that fits the content. Possible patterns include:

### Scroll storytelling
- ScrollTrigger reveals, scrubbed timelines, pinned narrative scenes.
- Horizontal project galleries controlled by vertical scroll.
- Vertical card stacking and overlapping editorial panels.
- Scroll-linked text progression and section progress indicators.
- Parallax layers and depth-based transitions.
- Snap points only when they improve orientation and never fight the visitor.

### Cards and 3D previews
- Perspective, layered transforms, controlled rotation, depth, and scale.
- Coverflow, stacked cards, spatial galleries, and interactive previews.
- Multi-layer box shadows and restrained red/blue lighting.
- Mouse tilt on pointer devices, with touch-appropriate alternatives.
- Real device/browser mockups only when they help explain the project.

### Typography and graphic motion
- SplitText and kinetic typography.
- Staggered line/word reveals and masked transitions.
- SVG path drawing, MotionPath, morphing, and animated diagrams.
- Flip transitions for meaningful layout/state changes.
- Observer or Draggable only where interaction requires them.

### Section transitions and ambient motion
- Timeline-based handoffs between sections.
- Layered image and color transitions.
- Controlled background movement and subtle ambient details.
- Continuous motion only when useful, pausable where appropriate, and disabled or simplified for reduced-motion users.

Use a small number of coordinated, high-quality effects. Every effect must have a purpose: explain, guide, reveal, compare, orient, or delight without obstructing content.

## 4. Scroll engineering rules

- Use GSAP timelines for coordinated sequences and ScrollTrigger for scroll-linked behavior.
- Use `scrub` only when visitors should directly control animation progress.
- Use `pin` only for a bounded, intentional storytelling moment. Calculate the duration from real content and viewport dimensions.
- Use `ease: "none"` for movement that must track scroll progress precisely.
- For horizontal tracks, calculate travel from actual content width and viewport width. Verify the first and last items, pin release, and section handoff.
- Use `containerAnimation` only within its documented constraints; verify trigger timing and supported animation properties.
- Avoid nested pins, overlapping triggers, blank pinned space, inaccessible last cards, and scroll hijacking.
- Refresh measurements after layout-affecting media loads or responsive changes when required.
- Avoid layout reads/writes in pointer-move loops. Prefer transforms and opacity for frequent animation.
- Keep one coherent scrolling architecture. Do not combine multiple smooth-scroll engines or override native scrolling without a clear requirement.

## 5. Responsive design is mandatory

Mobile is a first-class design target, not a compressed desktop layout. Design and test separate compositions for mobile, tablet, laptop, and wide desktop.

### Mobile
- Preserve natural vertical scrolling.
- Important sections must still respond meaningfully to vertical scrolling; do not leave the mobile experience static by default.
- Prefer vertical reveals, vertical card sequences, restrained parallax, perspective transitions, progress cues, and touch-friendly interactions.
- Do not force long pinned horizontal scenes onto narrow screens when they harm reading or navigation.
- Never rely on hover to expose essential content.
- Keep text readable, buttons touch-friendly, images well-framed, and controls inside safe areas.
- Prevent overlap, horizontal overflow, clipped card bottoms, and fixed elements covering content.
- Account for changing mobile browser chrome and short viewport heights.

### Tablet
- Re-evaluate spacing, grid density, card dimensions, and pin duration.
- Do not simply reuse desktop measurements when the composition no longer fits.

### Desktop and laptop
- Use side regions intentionally for meaningful metadata, navigation, progress, secondary previews, or visual framing.
- Use horizontal galleries and pinned scenes only when the available viewport supports them.
- Never waste large gutters or fill them with meaningless decoration.

Use `gsap.matchMedia()` or the project's established responsive helper. Revert media-specific animations correctly when breakpoints change.

Test at minimum: 320, 360, 375, 390, 414, 430, 768, 834, 1024, 1280, 1366, 1440, and 1600px widths when the environment permits. Also test short viewport heights and landscape orientation for pinned layouts.

## 6. Content must never be sacrificed

- Never hide, truncate, or remove real content to make an animation fit.
- Avoid restrictive fixed heights, `max-height`, `line-clamp`, and overflow clipping when they conceal descriptions, project details, technology tags, actions, or card bottoms.
- Verify every item in a gallery, especially the first and last items.
- Ensure shadows, focus outlines, controls, and lower card content are not clipped by parent containers.
- Essential details must be available without hover.
- Verify actual Arabic and English text lengths, mixed-direction content, punctuation, and RTL layout where applicable.
- SplitText or generated wrappers must preserve a complete accessible text representation.
- Reduced-motion mode must expose all content immediately and keep the page fully usable.

## 7. React, Next.js, and lifecycle safety

- Follow the project's established GSAP integration. Prefer `@gsap/react` and `useGSAP` when already used or appropriate.
- Scope selectors and animations to component roots.
- Clean up/revert timelines, ScrollTriggers, listeners, observers, pointer handlers, and media-query contexts on unmount and route changes.
- Avoid duplicate plugin registration and global selectors that affect unrelated components.
- Handle SSR and hydration safely; do not access browser-only APIs during server rendering.
- Avoid state updates on every animation frame when direct GSAP updates are appropriate.
- Keep animation code modular and explain non-obvious measurements or trigger calculations.

## 8. Performance, accessibility, and reduced motion

- Prefer transform and opacity for frequent animations.
- Use blur, filters, large shadows, and complex SVG effects sparingly.
- Reserve media dimensions and aspect ratios to prevent layout shifts and ScrollTrigger measurement errors.
- Lazy-load below-the-fold media appropriately.
- Respect `prefers-reduced-motion` for reveals, parallax, pinned scenes, smooth scrolling, and ambient loops.
- Reduced-motion mode must not leave content hidden or timelines incomplete.
- Provide pause/stop controls for non-essential continuous motion where appropriate.
- Preserve semantic HTML, keyboard navigation, visible focus, sufficient contrast, and touch access.
- Do not use color or movement alone to communicate essential state.

## 9. Visual quality standard

Before implementation, define for each major section:
- Its visual concept and focal point.
- What the visitor is meant to do: read, compare, explore, navigate, or interact.
- Its motion metaphor and why that metaphor fits the content.
- How its composition changes on mobile, tablet, laptop, and desktop.
- How the same content remains usable without motion.

Use intentional typography, spacing, negative space, surfaces, lighting, and depth. Side gutters should contain meaningful framing, navigation, progress, or metadata—not arbitrary decoration. Use red/blue lighting and layered shadows with restraint and maintain readable contrast.

A section is not premium merely because it contains glow, blur, 3D rotation, or many effects. It is premium when composition, content, movement, and usability work together.

## 10. Browser-based visual QA is required

Do not stop after TypeScript compiles.

When runtime and browser tooling are available:

1. Start the project using its existing scripts and environment.
2. Open the actual local website in a real browser.
3. Inspect the complete page from top to bottom at desktop, laptop, tablet, and mobile sizes.
4. Capture screenshots at representative viewports before and after changes.
5. Test slow and fast scrolling, every pin start/end, horizontal track endpoints, snapping, transitions, and section handoffs.
6. Test direct navigation, reload while scrolled, route changes, resize, image loading, touch, keyboard, and reduced motion.
7. Check every project's full details and every card's lower edge and controls.
8. Check for horizontal overflow, clipped shadows, blank pinned space, overlapping text, hidden buttons, and layout shifts.
9. Fix observed defects and repeat the review.

If browser access is unavailable, say so explicitly. Complete feasible static checks, but never claim visual verification without actually opening and inspecting the site.

## 11. Execution workflow

For substantial work, follow this sequence:

1. Audit repository, content, architecture, and baseline behavior.
2. Research current GSAP APIs and relevant references.
3. Define a distinct art direction for each major section.
4. Define responsive behavior before writing timelines.
5. Design reusable motion patterns and cleanup strategy.
6. Implement incrementally, validating representative sections before scaling the pattern.
7. Verify content completeness and accessibility.
8. Run browser QA across target viewports and fix defects.
9. Run available typecheck, lint, tests, and production build.
10. Report changed files, motion choices, responsive differences, actual viewport tests, commands/results, dependency changes, and remaining limitations.

Do not stop at a plan when implementation was requested. Make sensible, reversible decisions and proceed without unnecessary questions. Ask only when a genuinely essential project fact or permission is missing.

## Definition of done

- [ ] Every major section has an intentional, distinct visual concept.
- [ ] Motion supports the content and never obstructs navigation.
- [ ] Desktop, tablet, and mobile have deliberate responsive compositions.
- [ ] Mobile vertical scrolling remains natural and meaningful.
- [ ] All real content and project details remain visible and reachable.
- [ ] No clipped card bottoms, hidden last items, or broken horizontal endpoints.
- [ ] Reduced-motion mode exposes all content and remains usable.
- [ ] React/GSAP lifecycle cleanup is correct.
- [ ] Browser inspection was performed, or its exact blocker is reported.
- [ ] Build, lint, typecheck, and tests were run where available and results are reported honestly.

## Final report

Summarize:
1. What was audited and redesigned.
2. Distinct motion patterns used and why.
3. Desktop/tablet/mobile differences.
4. Content completeness checks.
5. Exact viewport sizes actually tested.
6. Commands run and real results.
7. Dependency/version changes and reasons.
8. Remaining issues or uncompleted checks.

Never claim “fully tested,” “all content visible,” or “production-ready” unless the corresponding checks were actually performed.
