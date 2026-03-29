# Show HN: MESA – A governance framework for running a company on AI agents

I'm a solo founder in Redmond, Oregon — also a working musician — and about a year ago I needed to run a real company on AI agents. Not tool-assisted humans. Agents as the team itself. Eleven of them. No template existed.

So I built one. The hard way.

MESA is a governance framework for multi-agent companies. It's not theoretical. It runs in production right now, governing 11 AI agents building a real SaaS product called GigBoom. It exists because something went wrong in nearly every session during the first three months, and I kept fixing what broke until the fixes became a system.

**The core insight** is simple: agents carry nothing between sessions. They read everything they know from files at startup. That means your governance files aren't documentation — they're your company's brain. Every correction makes every agent smarter immediately because they all read the same files. An agent arriving on day one has the same institutional knowledge as one that's been running for months.

That principle drives every design decision in MESA.

**Here's what the framework gives you:**

The governance files sit at the center of concentric rings — intent layer (founder and strategic advisor), orchestration (COO and CTO), execution (builders), gates (independent verification), and observation (nervous system). Authority flows inward. Work flows outward.

Owner's intent encoding captures how you actually think — calibrated with percentages showing how confident to apply each principle. "Honesty is immediate — 100%" tells agents to apply that with full confidence. "Simplicity wins — 70%" tells them the reality is more nuanced. You include honest gaps where you say one thing but do another. That's operational intelligence, not criticism.

Socratic briefs go to decision-makers (they reason independently before seeing your thinking). Directive briefs go to executors (thinking is done; build to spec). Two different patterns for two different roles.

The learning system doesn't bloat governance by codifying every fix. Fix immediately, always. Log everything. When the same issue appears three times in a week, it becomes a permanent playbook entry. One occurrence is an incident. Three is a pattern that earns knowledge.

Checkpoints are mechanical, not behavioral. Four-question test: Is it automatic? Does it hold under momentum? Does it have a specific trigger? Does it produce an artifact? If any answer is no, it gets redesigned until it's mechanical. Behavioral checkpoints fail exactly when they matter most.

**What's in the repo:** Full architecture docs, templates, the six pillars, the concentric rings model, calibration patterns for owner encoding, Socratic and directive brief structures, the learning flywheel, the three-occurrence threshold system, health check patterns. Give away the knowledge. If you're building multi-agent systems, this might save you three months of painful discovery.

**The honest part:** MESA isn't perfect. It's useful. It's been pressure-tested across 30+ sessions and multiple product builds. It emerged from real problems, not a whiteboard. Every piece traces back to something that actually broke.

If you're running multi-agent systems or thinking about it, I'm curious: what governance patterns have you found that work? What breaks that a framework like this would prevent? The more I understand where you've hit friction, the more useful we can make this.

Repo: [LINK — Phillip inserts GitHub URL before posting]

Docs are complete. Let me know what you find.
