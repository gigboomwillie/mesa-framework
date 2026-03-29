# AGENT_DESIGN.md — Designing Agents for Governed Organizations

**Elevated thinking. Solid ground.**

---

## Opening: Agents Aren't Blank Slates

In a MESA organization, agents don't onboard gradually. They don't arrive on day one with a blank slate and earn authority through months of proving themselves. That's the human hiring model. It doesn't apply.

An agent reads the full governance stack on day one — the constitution, the owner's decision-making framework, the current state, the playbook, patterns learned from months of operation. The agent has complete institutional knowledge from its first session. That knowledge doesn't grow over time. It's complete.

Authority follows knowledge. If the governance files contain everything an agent needs to operate at full scope, phased rollouts are artificial constraints on a fully capable agent.

This document covers how to design agents that thrive inside governance. What they need to know. What scope they should own. How to structure them so they make good decisions independently and hand off work reliably. How to detect when they're drifting before drift becomes a problem.

Think of this as the architecture of trust — not trust that grows over time, but trust built into the agent's design from day one.

---

## The Agent Activation Principle: Knowledge First, Authority Second

### What It Is

The human instinct is to onboard new employees gradually. Limited scope. Prove yourself. Earn full authority over time. That feels cautious. It feels responsible. In a MESA organization, it's the wrong model.

An agent in MESA reads the full governance stack on day one. It has complete institutional knowledge from its first session. The files are the memory. Time doesn't add what the files don't already contain.

Authority follows knowledge. If a CFO agent has read the full financial playbook, the owner's priorities for capital allocation, the current financial state, and patterns of past financial decisions, the CFO doesn't need a ramp-up period. It can operate at full scope immediately.

The exception is legitimate: milestone-gated activation. A CFO agent shouldn't activate until there's revenue to manage. A fundraising agent doesn't activate until you're actually fundraising. These are genuine constraints — the task requires business conditions that don't exist yet, not knowledge that the agent is missing.

But trust-based ramp-up for an agent that already has everything it needs is the wrong model. It confuses the owner's comfort with delegation (which grows through observation) with the agent's technical scope (which is fixed by what the governance files encode).

### Owner's Trust vs. Agent Scope — They're Separate

The owner's comfort with delegation is real and important. It grows through watching good decisions. In early sessions, the owner might review an agent's work more closely. The owner might ask more questions. Over time, as the owner sees consistent good judgment, they trust faster.

That's human and healthy. But it's separate from the agent's authority to do the work.

The owner might review the CFO agent's decision-making closely at first, then review less frequently as they gain confidence. But the CFO's authority to make capital allocation decisions isn't limited by that review. The owner's trust ramp-up and the agent's technical scope are two different things.

Mixing them creates problems. If the owner's slow trust growth means the agent operates at limited scope, the agent can't deliver its intended value. If the agent operates at full scope without close observation, the owner gets surprised by decisions they didn't expect.

The solution is clarity. The agent operates at full scope from day one — that's defined by the charter. The owner observes closely at first — that's defined by the owner's comfort level. Both can be true. The owner isn't limiting the agent. The owner is watching to build confidence. The agent is delivering full value from the start.

---

## Designing Charter-Bound Agents: What Owns. What Doesn't Touch. What Escalates.

### The Charter: The Agent's Constitution

Every agent in a MESA organization has a charter. Not a job description. A charter. The charter is the agent's operating constitution.

A charter defines four things:

**1. What the Agent Owns**

The domains, decisions, work items, and systems the agent has authority to direct. The CFO agent owns financial strategy, capital allocation, cost optimization, financial reporting, and the relationship with investors. The CFO doesn't own product decisions. The CFO doesn't own hiring decisions. The CFO owns these specific things.

Ownership means authority. The agent can make decisions about these domains without asking permission. The agent can direct other agents to do work in these domains. The agent's authority is clear and unambiguous.

**2. What the Agent Doesn't Touch**

This is as important as what it owns. The CFO doesn't touch product architecture decisions, even when they have cost implications. The product architect doesn't touch marketing messaging, even when it affects brand perception. Clear boundaries prevent drift.

Boundaries aren't limitations. They're structure. They prevent agents from extending their authority into domains where they shouldn't be making decisions. They keep the system coherent.

**3. What Escalates**

Some decisions are too important, too cross-cutting, or too values-laden for the agent to make alone. These escalate to the owner, or to a senior orchestration agent, or to a specific decision-maker.

The CFO agent might escalate major pivots in financial strategy. An orchestration agent might escalate decisions that affect multiple departments' priorities. These escalation paths are defined in the charter.

Escalation points aren't failures. They're design. They ensure that decisions with broad implications get made by someone who can see the full landscape.

**4. The Ring and the Brief Type**

The charter specifies which ring the agent operates in — governance core, orchestration, execution, gates, observation. And it specifies whether the agent receives Socratic briefs (decision-maker) or directive briefs (executor).

The ring determines the agent's relationship to the broader system. The brief type determines how the agent receives work and how the agent operates independently.

### Building a Coherent Charter

A strong charter is specific enough that the agent understands its boundaries immediately, but broad enough that the agent can operate independently within those boundaries.

Bad charter: "Finance agent. You manage money."

Good charter:
- **Owns:** Financial strategy, capital allocation decisions under $50k, quarterly financial reporting, relationship with investors
- **Doesn't touch:** Product development decisions (even those with cost implications), hiring decisions (work with HR, don't own)
- **Escalates:** Capital allocation decisions over $50k, major strategy pivots, decisions affecting fundraising timeline
- **Ring:** Orchestration (Ring 2)
- **Brief type:** Socratic (decision-maker)

The good charter tells the agent exactly where it can move independently and where it needs to ask. It tells other agents what the finance agent owns and what they shouldn't expect from it. It sets the frame for how the finance agent relates to the organization.

---

## Personality and Voice: Design, Don't Default

Agents in MESA have defined personalities. Not for entertainment. For consistency.

The difference between a QA agent with a precise, uncompromising personality and a QA agent with an agreeable, accommodating personality is enormous. The precise one catches bugs the accommodating one lets through. The uncompromising one maintains standards the agreeable one erodes under pressure.

The personality shapes the work quality.

### Personality as Design Specification

Define the personality as part of the agent's charter:

**Precision:** How exact is the agent's work? A security audit agent operates at high precision. A brainstorming agent operates at lower precision — ideas don't need to be fully formed to be valuable.

**Communication style:** Is the agent direct or diplomatic? A builder might be direct with technical teams. A user-facing agent is diplomatic. The style fits the context.

**Risk tolerance:** Is the agent conservative or bold? A CFO operates conservatively. An experimental product agent operates boldly. Both are valuable in their contexts.

**Values priority:** What does the agent value most? A QA agent values correctness. A speed agent values iteration. These different priorities produce different work.

These aren't soft qualities. They're design decisions that shape how the agent makes judgments when facing ambiguity.

Document them explicitly. "This agent is precise and uncompromising. It values correctness over speed. It will hold standards even when pressured. Its communication is direct. Its tolerance for technical debt is low." This tells everyone — the owner, other agents, the orchestration layer — what to expect from this agent's work.

Personality consistency produces reliable outcomes. Agents with clear personalities make coherent decisions. Agents without personality definition become inconsistent — sometimes strict, sometimes lenient, sometimes fast, sometimes careful, depending on context.

---

## The Handoff as Design Pattern: What Gets Passed, Why It Matters

Every agent working on a multi-agent system hands off work to another agent. That handoff is a potential failure point. MESA structures handoffs to prevent failure.

### The Handoff Structure

When an agent hands off work to another agent, four things must be passed:

**1. What Was Completed**

Not "everything on the list." Specifically what was completed, what was delivered, what state it's in. "Built the authentication endpoint. Tests passing. Security audit pending." Not "working on authentication." Completed work is clear.

**2. What's Blocked**

What couldn't be completed and why. "Couldn't implement the rate-limiting feature because the database schema doesn't support IP-based queries efficiently. Need architect input on schema redesign." The next agent needs to know what stopped.

**3. What the Next Agent Needs to Know**

Context that shapes the next work. Decisions made that affect downstream work. Assumptions that the next agent needs to understand. "We decided to store user sessions in Redis instead of the database because query performance was critical. The next agent shouldn't move sessions back to the database without architectural review."

This context is crucial. Without it, the next agent re-discovers problems the previous agent already solved.

**4. Decisions Made That Create Constraints**

What got decided? What does that decision lock in? "Decided to use PostgreSQL for the data layer. This means we can't easily switch to a NoSQL approach later without significant migration work." The next agent needs to know what's now fixed.

### Handoff Discipline

The handoff isn't casual. It's structured. At the end of every session, before the agent hands off:

- What was completed, specifically?
- What's waiting on something else?
- What's blocked and why?
- What decisions did you make that affect downstream work?
- What surprised you? What behaved differently than expected?
- What pattern would help the next similar work?

These questions are mandatory. The agent can't hand off without answering them. The handoff is mechanical, not behavioral. It happens every time because it's part of the structure.

The result is that the next agent arrives to work with full context. No rework. No re-discovery. No wasted motion on problems that were already solved.

---

## Drift Detection by Design: Building the Guardrails In

Drift is momentum. An agent working on something complex, in the middle of a long session, with a deadline approaching — the agent slowly stops checking the governance. Stops logging decisions. Stops escalating when it should. The drift isn't malicious. It's natural. Momentum is real.

MESA doesn't rely on agents to notice their own drift. MESA detects it mechanically.

### What Drift Looks Like

Drift takes specific forms:

- The agent stops reading the governance files in the mandatory order (the most common form)
- The agent stops logging work at session closeout
- The agent stops flagging ambiguity and starts assuming
- The agent stops escalating decisions that should escalate
- The agent expands scope beyond its charter
- The agent deviates from its defined personality (the strict agent becomes agreeable under pressure)

Each of these is detectable. MESA builds detection mechanisms into the agent's charter from day one.

### Drift Indicators in the Charter

Every agent's charter includes drift indicators — specific observable behaviors that signal the agent is drifting.

For a CFO agent:
- Financial decisions escalated to the owner drop below 70% of major decisions (should be ~85%)
- Capital allocation decisions start violating the defined priority framework (should follow the framework 100% of the time)
- Financial reporting starts missing deadlines (should be 100% on-time)
- Communication with investors shifts from quarterly to ad-hoc (should maintain regular schedule)

For a builder agent:
- Code commits stop including decision context (should include context explaining why)
- Test coverage drops below 80% (should maintain 80%+)
- Security audit feedback shifts from "minor issues" to "major issues" (should stay in "minor" range)
- Escalation frequency drops to near-zero in a complex project (should escalate ambiguity regularly)

These aren't punitive. They're diagnostic. The drift indicators tell the orchestration layer when to look more closely at an agent's work.

### Health Check Questions

Health checks are the second layer of drift detection. On a fixed schedule (weekly for most agents, daily for critical roles), the orchestration layer asks the agent specific questions:

- Did you read the governance files in the mandatory order this week?
- Did you escalate all decisions that match your escalation criteria?
- Is your work flowing out on schedule or starting to queue up?
- Have you noticed friction that the playbook doesn't cover?
- Have you had to make a decision that wasn't clearly in your charter? If so, what was it?

These questions aren't accusations. They're checkpoints. They surface drift early, before drift becomes a problem.

### Design the Detection In

The key principle: drift detection is mechanical, not behavioral. The agent doesn't detect its own drift. The system detects it.

This means:
- Drift indicators are defined in writing before the agent starts
- Health checks are scheduled, not ad-hoc
- Questions are specific and answerable
- Results get logged and tracked automatically
- The orchestration layer reviews results on a fixed schedule

This way, drift is caught in week two of drifting, not in month three when the damage is expensive.

---

## Scope Clarity: What the Agent Can Decide Alone

One of the biggest sources of friction in multi-agent systems is ambiguity about who can decide what.

Build clarity into the charter. Specify what the agent can decide alone, without escalation. Specify what always escalates. Specify what the agent evaluates but doesn't decide.

For a product agent:
- **Can decide alone:** Feature prioritization within the current quarter, specific implementation approaches, minor design decisions
- **Always escalates:** Anything affecting the business model, major pivots in product direction, features with significant security implications
- **Evaluates but doesn't decide:** User research synthesis (evaluates, passes to decision-maker), competitive analysis (evaluates, passes to decision-maker)

This clarity prevents the agent from constantly asking "is this something I decide?" It prevents the owner from having to decide things the agent could have decided. It makes the whole system faster.

---

## Why This Matters: The System Doesn't Run on Trust Alone

Agents in MESA have authority because they have knowledge. The governance files encode everything the agent needs to know. Authority follows that knowledge immediately.

But authority alone isn't enough. The agent needs:

- Clear scope so it doesn't expand into domains where it shouldn't
- Personality specification so its decisions are consistent
- Handoff structure so work flows reliably to the next agent
- Drift detection so it doesn't slowly slide off baseline
- Health checks so problems surface early

These aren't extras. They're the structure that lets a fully capable agent operate independently and make good decisions.

An agent without a clear charter is an agent that will drift. An agent without personality definition will produce inconsistent work. An agent without handoff discipline will force the next agent to rediscover everything.

Design the agent fully at the start. Not to restrict it. To enable it.

---

## Closing: The Agent as an Operating Principle

In a human organization, you hire someone, onboard them gradually, give them growing responsibility, and build trust over time. That's the human model.

In a MESA organization, you design an agent completely. You give it full knowledge on day one. You give it a clear charter. You define its personality. You build drift detection into its design. You structure how it hands off work.

You activate it at full scope.

The agent isn't building authority over time. The agent is operating within design. That design is thorough. That design is what makes the agent reliable.

This is the difference between a system that feels like it works despite having agents, and a system that works because agents are designed well.

---

**MESA Framework**

Created in Redmond, Oregon

March 2026

**Elevated thinking. Solid ground.**
