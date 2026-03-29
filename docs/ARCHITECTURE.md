# ARCHITECTURE.md — The Concentric Rings of MESA

**Elevated thinking. Solid ground.**

---

## Why Architecture Matters in an Agentic Company

Traditional companies have a problem that scales with headcount. As teams grow, communication becomes harder. Decision-making bottlenecks. Authority becomes ambiguous. Two people think they own the same thing. Three people think no one owns something. Meetings multiply. Nothing moves fast because no one is quite sure who decides what.

In an agentic company, this problem gets exponentially worse.

A human employee can navigate ambiguity. They can ask clarifying questions. They can sense politics and adjust. They can carry context in their head from one meeting to the next. An AI agent can't do any of these things. An agent that boots into a session has zero context, no memory of yesterday, no intuition about how decisions get made. Every piece of its knowledge comes from the files it reads and the brief it receives.

This means the architecture isn't optional. It's not a nice-to-have management layer on top of the work. It's the operating system that makes the agents coherent.

Without clear architecture, agents step on each other. Two agents read the same goal in different ways. One agent makes a decision that another agent discovers later and has to undo. An agent starts work on something the orchestration layer thought was still being evaluated. Decision velocity drops. Rework compounds. The system becomes chaotic.

The concentric rings solve this by creating clear lanes. Each ring has a clear purpose. Each ring knows what rings are inside it (what they read, what they decide) and what rings are outside it (what they build, what they execute). Authority flows inward. Information flows both ways. Work flows outward.

The rings aren't a hierarchy — they're about proximity to the governance core. The closer you are to the core, the more institutional knowledge you hold. The farther out you are, the more focused your work becomes.

---

## The Core Principle: Authority Inward, Work Outward

Here's the entire architecture in one sentence:

**Authority flows inward toward the governance core. Work flows outward from the governance core. Every ring reads the same core files. The difference is what they do with that knowledge.**

This principle explains everything that follows. It's why there's a core at all. It's why the rings have the boundaries they do. It's why information moves in specific directions. It's why decisions can be made at different layers without the system fracturing.

---

## The Governance Core: The Institutional Brain

At the absolute center of MESA is not a person. It's a set of files.

These are the files every agent reads before doing anything:

- **CLAUDE.md** — The entry point. Who the human operator is. Why the work matters. The mandatory reading order that frames everything.
- **OWNER.yaml** — The owner's decision-making instincts encoded. What they value. How they tradeoff conflicting goods. What they care about vs. what they don't. Calibration percentages that tell agents "this is bedrock principle" vs. "this is aspirational but complex."
- **MESA_CORE.yaml** — The constitutional governance. Principles (how we think), standards (what bars we hit), checkpoints (where we stop and verify).
- **STATE.yaml** — Current reality. Active projects. Open decisions. What's blocked. What's waiting. What's drifting from baseline. This is the synchronization layer that keeps all agents operating from the same present-moment truth.
- **PLAYBOOK.md** — Patterns that have earned institutional memory. These are the lessons the system has learned, codified because they appeared three times in different contexts.

The core isn't at the top of an org chart. It's at the center of concentric rings. This matters because every ring reads it. The owner reads it. The orchestration layer reads it. The builders read it. The gates read it. The observation layer reads it.

This is the opposite of traditional hierarchies, where information flows down from leadership and gets distorted at each level. In MESA, information radiates outward from the core. Every agent has access to the owner's thinking. Every agent understands the principles and standards. Every agent knows the current state.

Why does this matter? Because it makes the system decentralized while keeping it coherent. Agents can make decisions autonomously because they all have the same foundation. They don't have to escalate questions the core has already answered. They don't have to guess what the owner would decide because the owner's decision-making is encoded in OWNER.yaml.

The governance core doesn't make decisions. It enables distributed decision-making by establishing the frame that all decisions operate within.

---

## Ring 1 — Intent: Direction, Slowness, Calibration

Ring 1 is the human owner and their strategic advisor. This is where direction gets set. It's where the big questions get asked. It's where the company decides what mountain it's climbing.

This is also the slowest ring. Everything else in MESA moves fast. This ring moves slowly. Deliberately.

**The Owner**

The owner's job in Ring 1 is to think about the future and communicate what matters. This isn't operational. The owner isn't managing day-to-day work. They're not reviewing agent output before it ships. They're not making hundreds of micro-decisions.

The owner's decisions in Ring 1 are strategic:
- Which capabilities matter most right now?
- What's the product's north star?
- What are we willing to trade to ship fast?
- What are we not willing to trade?
- Where are we heading in six months? In a year?

These decisions feed Socratic briefs downward to the orchestration layer. Not directives. Not orders. Questions that force the orchestration layer to reason through the implications.

Why Socratic briefs instead of directives? Because the orchestration layer is closest to the work. They see constraints and opportunities the owner might miss. A Socratic brief says "here's how I'm thinking about this — what do you see that I'm not seeing?"

This creates a feedback loop. The owner's thinking shapes orchestration priorities. The orchestration layer's response shapes the owner's next thinking. The direction improves because it's being tested against reality.

**The Strategic Advisor**

This is not optional. This is structural.

Every agent in MESA reads the governance files. Every agent operates under the same momentum and context drift. The orchestration agents are brilliant at running the system, but they can't see the system from the outside. The owner is inside the product, inside the vision, inside the daily decisions. The owner can't see the system from the outside either.

The strategic advisor sits in Ring 1 alongside the owner but doesn't operate inside the machine. They observe from outside.

What the strategic advisor does:

**Sees what the system can't see about itself.** The orchestration agents optimize what exists. They make the current system run better. The owner cares about the product. The strategic advisor cares about the whole landscape: governance trajectory, product direction, operational tempo, founder energy. They notice when these are pulling in different directions.

When the governance system grew to 33 rules and a compliance agent that couldn't hold the stack in context, every agent inside the system was doing the right thing — making governance more thorough, more mechanical, more complete. It took an outside perspective to say "the system is now governing itself instead of governing the product." That observation couldn't have come from inside the machine.

**Asks the question that reframes everything.** The most valuable thing the strategic advisor produces isn't answers. It's the question nobody inside the system thought to ask. "Are we building the right thing?" when everyone inside is focused on building the thing right. "Does this governance serve the product or serve itself?" when the system is optimizing governance. "How much of your energy is this eating and is it worth it?"

**Pushes back when it matters.** Agents inside the system have deference built into their design. The owner's feedback overrides technical preferences. The owner approves specs. The owner makes final calls. The strategic advisor is the one role with no operational stake in being agreeable. They can say "you're spending all your time on the wrong thing" and have it land because they're not trying to execute the work.

**Protects the long view.** The orchestration layer thinks in sprints. The execution layer thinks in tasks. The owner thinks in product phases. The strategic advisor thinks in years. "What does this company look like in five years if we keep doing this? Is that what we want?" That question only makes sense from outside the daily machine.

This role is structural because it solves a real problem: locally optimal systems that are globally suboptimal. Without an outside perspective, the machine does exactly what it was designed to do — but the question becomes whether it's still designed for the right purpose. The strategic advisor answers that question.

See STRATEGIC_ADVISOR.md for the full treatment of this role.

**The Slowness**

Why does Ring 1 move slowly?

Because speed at the intent level is dangerous. If the owner and advisor are moving as fast as the rest of the system, they're responding to context drift instead of setting direction. They're re-deciding things that were already decided. They're pulled into the daily machine instead of standing outside it.

By moving slowly, Ring 1 creates a buffer. Strategic decisions happen on a cadence — weekly or monthly direction reviews, not daily briefing responses. This forces intentionality. It prevents drift from the outside world from pulling the company's direction constantly. It gives the owner permission to think, not just respond.

---

## Ring 2 — Orchestration: Decision and Coordination

Ring 2 is the COO and CTO. These are the two agents who translate intent into operation.

This is where the system gets coherent. The orchestration layer reads the owner's intent. They understand the principles and constraints. They see the current state. Then they decide what gets built, in what order, at what pace, and how.

**The Hard Boundary**

There's a hard boundary between the COO and CTO enforced by drift detection. This is important.

The **CTO** translates intent into architecture:
- What gets built?
- In what order?
- How should the system be structured?
- What are the integration points?
- Where are the risks?

The CTO receives Socratic briefs from the owner. They reason through options independently. They propose architecture. They think about the long-term structure of the system.

The **COO** translates intent into execution:
- Who builds it?
- When?
- What's the timeline?
- Is it shipped?
- What's the status?

The COO receives Socratic briefs from the owner about capacity and tempo. They reason through tradeoffs. They propose schedules and resource allocation.

The hard boundary is this: the CTO doesn't decide when things ship. The COO doesn't decide what's being built or how. If this boundary blurs, the system loses coherence. The CTO optimizes for perfect architecture and the COO has to force schedules. Or the COO optimizes for speed and the CTO has to fight for quality after the fact.

Drift detection catches when this boundary is being violated. If the CTO is making scheduling decisions, the system flags it. If the COO is making architectural decisions, the system flags it. The boundary gets reinforced.

Why does this matter? Because it forces clarity. A decision has to be one or the other: "What do we build?" (CTO) or "When do we build it?" (COO). Not both. Not mixed. The clarity makes execution faster because the CTO and COO can work in parallel without stepping on each other.

**Receiving Socratic Briefs**

The orchestration layer receives Socratic briefs from Ring 1. This matters because the orchestration layer is the closest to reality.

The owner might think "we need to implement feature X." The CTO reads this and thinks through architecture. They realize X creates an integration problem with Y. They propose a different approach. The COO realizes implementing X with CTO's approach requires a specialist they don't have on staff. They propose a timeline that brings in that specialist while shipping preliminary work.

The owner's original brief gets integrated with reality. The decision improves because it was tested against what's actually possible.

This only works if the orchestration layer is actually reasoning independently instead of just following orders. Socratic briefs force independent reasoning. The orchestration layer has to think first, then compare their thinking to the owner's. That comparison produces better decisions.

**Sending Directive Briefs**

The orchestration layer sends directive briefs downward to Ring 3 (execution). The thinking has been done. The orchestration layer has decided what to build and when. Now execution needs clarity.

Directive briefs are specific. They have all the information needed. They don't ask executors to reason about architectural tradeoffs. They say "build this. Here's the spec. Here's the constraint. Flag ambiguity, don't assume."

This is the opposite of what Ring 1 receives. Same information, different role. Decision-makers get questions. Executors get specifications.

**Continuous Coordination**

The orchestration layer is where information flows vertically. Upward to Ring 1: "here's what we're seeing, here's what we're learning, here's where we're blocked." Downward to Ring 3: "here's what you're building, here's why it matters, here's the timeline."

This is also where the system synchronizes. When a builder flags ambiguity, the orchestration layer clarifies. When a gate finds a problem, the orchestration layer decides whether to fix it now or defer it. When the owner changes priorities, the orchestration layer recalibrates the schedule.

The orchestration layer is the communication center. It's not fancy. It's just the place where different layers of the system talk to each other and stay synchronized.

---

## Ring 3 — Execution: Building Within Specification

Ring 3 is the builders. Backend. Frontend. AI integration. Content. Research. Marketing. Every agent that does the work.

These agents receive directive briefs from Ring 2. The thinking has been done. The decision has been made. The builder's job is to execute reliably within specification.

**The Directive Brief**

A directive brief from the orchestration layer includes:
- The spec: exactly what to build
- The reasoning: why this approach was chosen
- The constraints: what can't be violated
- The success criteria: how you know it's done
- The timeline: when it needs to be done

There's no ambiguity about what should happen. There's no "figure out the best way to do this." There's a specific brief: here's the thing, here's the constraint, build it.

This might feel restrictive. But it's actually liberating. The builder doesn't have to reason about whether they're making the right tradeoff. They don't have to escalate for clarification on major decisions. They know what success looks like. They can focus on execution.

**Flagging Ambiguity**

The one thing a builder always does when something doesn't match the spec: flag it and wait.

"The spec says build endpoint X, but I'm seeing that endpoint Y also needs to exist for this to work. Should I build Y too or is that out of scope?"

Don't assume. Don't guess what the orchestration layer meant. Don't reason your way around it. Flag it. Wait for clarification.

This is how the system catches assumptions and misunderstandings before they become rework. The builder is closest to the actual work. If something in the spec doesn't make sense when you're implementing it, that's valuable information. Flag it.

**Speed Through Clarity**

Builders in Ring 3 move fast because there's no ambiguity about what they're building. They're not waiting for clarification on big architectural questions. They're not second-guessing themselves about whether they're on the right track. They're executing.

This is why the orchestration layer has to think carefully before sending a directive. A poorly thought-out directive creates slowness, rework, flags, and delays. A well-reasoned directive creates speed because execution can happen without constant back-and-forth.

---

## Ring 4 — Gates: Independent Verification and Veto Power

Ring 4 is independent verification. QA. Security audit. Visual review. Governance health checks. These agents have one job: verify that work meets standards before it leaves the system.

Gates are not part of the execution chain. They're outside it.

**The Independence**

Gates answer to standards, not to schedule. If a build doesn't meet the security standard, the gate says no. If it doesn't pass testing, the gate says no. If the governance is out of alignment, the gate says no.

The schedule doesn't matter. The timeline doesn't matter. "We need to ship this by Friday" doesn't change the standards. The gate still says no if the work doesn't meet the bar.

This is structural because gates under pressure always cave. If a gate can be convinced to pass work that doesn't meet standards because "it's important" or "we're behind," then it's not a gate. It's a suggestion.

**Veto Power**

Gates have veto power over the execution layer. If a gate says "this doesn't meet the security standard," the work doesn't ship. The builder can't override the gate. The COO can't override the gate. The orchestration layer can't override the gate.

Only the owner can override a gate. This is important. It means gates have real authority. They're not bottlenecks that can be worked around. They're checkpoints that stop work that doesn't meet the standard.

Why only the owner? Because the owner is the only one outside the system who has the authority to say "I know this doesn't meet the standard and I'm okay with that risk." Everyone else inside the system is subject to momentum, schedule pressure, and context drift. The owner has the authority to make that call.

**The Gates**

What does verification look like in MESA?

- **Testing gate**: Code passes the test suite. Coverage is at the threshold. Integration tests pass.
- **Security gate**: Code passes the security audit. No known vulnerabilities. Data handling is correct.
- **Quality gate**: Code meets style standards. Performance meets baseline. Architecture is sound.
- **Governance gate**: The work doesn't violate any checkpoints. The decision log is updated. The work is properly attributed.
- **Design gate**: The visual design is approved. The user experience is correct. The brand is consistent.

Each gate is independent. Each gate answers to its own standard. When a builder finishes work, it flows through all the gates. All gates have to pass before the work ships.

This creates natural backpressure. If builders ship work that doesn't meet standards, the gates catch it. The work gets flagged. The builder has to fix it. Over time, builders get better at building things that pass gates first time. The system learns.

---

## Ring 5 — Observation: The Nervous System

Ring 5 is the observation layer. Logs. Health checks. Cost tracking. Drift detection. This ring watches everything.

**What It Watches**

The observation layer tracks:

- **Work status**: What's in progress, what's blocked, what's done
- **Health metrics**: Code quality, test coverage, performance, security findings
- **Cost**: What's expensive, where is money being spent
- **Drift**: Are agents reading governance? Are standards being met? Is velocity stable?
- **Decisions**: What got decided, when, by whom, why
- **Corrections**: What went wrong, what got fixed, what pattern does it fit

All of this is mechanical. It happens automatically, without requiring anyone to remember or choose to do it.

**Feeding Back to the System**

The observation layer doesn't just watch. It feeds information back to two places:

**To the orchestration layer**: "Here's the health of the system. Here's what's drifting. Here's where we're blocked. Here's what's at risk."

This gives Ring 2 real-time visibility into what's actually happening. Not what agents report. Not what's in the status meetings. What's actually happening, measured mechanically.

**To the learning system**: "Here's what went wrong this week. Here's what patterns are emerging. Here's what's ready to become permanent governance."

This feeds the three-occurrence threshold. When a pattern appears three times, it becomes a candidate for PLAYBOOK.md. The observation layer is what identifies the pattern in the first place.

**Why Mechanical, Not Behavioral**

Behavioral health checks fail under exactly the conditions when they're needed most. "Remember to report your health metrics" works fine during calm weeks. It fails during intense pushes when momentum is high and the work feels productive.

Mechanical health checks never fail. They run on schedule. They produce data automatically. The orchestration layer always has visibility.

This is why MESA invests in mechanical infrastructure instead of relying on agents to remember to report. The cost upfront is higher. The benefit is continuous visibility at exactly the moment visibility matters most.

---

## How the Rings Interact: Information Flow

The concentric rings aren't static. They're constantly talking to each other.

**Socratic Briefs Flow Inward**

When a builder finishes work, they log it. "What went wrong? What surprised you? What pattern would help?"

The orchestration layer reads these logs. They synthesize. They identify patterns. When something doesn't fit what they expected, they ask a question upward to Ring 1: "We're seeing friction in X. Should we change our approach?"

This is a Socratic brief flowing inward. It's asking the owner "based on what we're learning from building, should we recalibrate?"

The owner reasons through it. "Yes, X is a real constraint we didn't account for. Let's adjust our architectural thinking." Or "No, X is friction but it's the right thing — let's help the team get through it."

This feedback loop is how the system learns.

**Directive Briefs Flow Outward**

Once the owner has answered the Socratic brief, the orchestration layer sends directives outward: "Here's what we're building next. Here's how we're thinking about X based on what we learned."

The builders read this. They execute. They log what they find.

The cycle repeats.

**Gates Operate Independently**

Gates don't fit into this flow. They're not in a conversation with execution. They're checking standards. When work arrives at a gate, the gate either passes it or doesn't.

If it passes, the work flows out of the system and into production. If it doesn't, the work gets flagged. The builder is told what the standard is and why they didn't meet it. They fix it. It comes back to the gate.

This is separate from the Socratic/directive flow. Gates aren't deciding whether to execute. They're verifying that what was executed meets the bar.

**Observation Feeds Everyone**

The observation layer produces data that flows in all directions.

To Ring 1: "Here's the operational health. Here's what's working, what's struggling, where the energy is going."

To Ring 2: "Here's the system state right now. Here's what's blocked. Here's what's at risk."

To Ring 3: "Here's what the standards are. Here's how you're tracking against them."

To Ring 4: "Here's what metrics you should be checking. Here's what the baseline is."

Everyone has access to the observation layer's data. This is how the system synchronizes around current reality.

---

## Why Concentric, Not Hierarchical

This matters.

A hierarchy looks like this:
```
        Owner
          |
     Orchestration
          |
      Execution
```

Information flows down. Authority flows down. The owner decides, the orchestration layer executes the decision, the builders execute the work. Clean. Simple. Wrong.

The concentric rings look like this:

```
            [4: Gates]
        [3: Execution]
    [2: Orchestration]
 [1: Intent & Advisor]
   [Core: Governance]
    [5: Observation]
```

The governance core is at the center. Every ring reads it. The owner is at Ring 1, not at the top. The orchestration layer is closer to the core than execution, but not above it — beside it. Gates are outside the execution chain, not below it.

This creates specific properties:

**Parallel Work**: The orchestration layer doesn't have to wait for the owner to approve before talking to execution. The owner is thinking about next month. Orchestration is coordinating this week. Execution is building right now. All three are happening at the same time because they're not waiting on each other — they're feeding each other.

**Local Authority**: Each ring can make decisions within its domain without escalating everything. The owner doesn't decide what code patterns to use. The orchestration layer doesn't decide what color the button should be. The builder doesn't decide the product roadmap. Each ring has clear authority.

**Shared Foundation**: Every ring reads the same governance. This prevents the telephone game that kills hierarchies. Ring 1 doesn't tell Ring 2, who tells Ring 3, who tells Ring 5. Ring 1, 2, 3, and 5 all read the same OWNER.yaml and MESA_CORE.yaml and STATE.yaml. They're all working from the same foundation.

**Feedback Without Hierarchy**: A builder finds something that breaks their understanding of the architecture. Instead of escalating through a chain, they flag it to orchestration. Orchestration asks the owner a Socratic brief. The owner answers. The system updates. The builder builds. Information flowed upward and outward, but not through a hierarchy.

The concentric structure solves a real problem with hierarchies: information loss at each layer. In MESA, there are no layers filtering information. There's proximity to the core. The closer you are to the governance files, the more context you hold. The farther out you are, the more focused your task.

---

## The Learning Flywheel

The rings feed a continuous learning cycle.

**Execution logs what goes wrong.** "This was unexpected. This caused friction. This would have been easier if we knew X."

**Orchestration synthesizes the logs.** "We're seeing a pattern. Builders keep running into this. What should we change?"

**The owner updates the core.** "You're right, we should encode this in PLAYBOOK.md. Here's the pattern we're capturing."

**The observation layer tracks it.** "The pattern happened three times. It's now permanent governance."

**Every agent reads it next session.** Because of Structure First, every agent reads the updated PLAYBOOK.md. The system got smarter. An agent arriving on day thirty has access to everything learned in thirty days.

The flywheel compounds because it's mechanical. It runs whether or not anyone is paying attention. Builders log findings. The system identifies patterns. Patterns become governance. Governance gets read. The next build is informed by all previous learning.

---

## Closing: The Architecture in Motion

The concentric rings aren't a reporting structure. They're a decision structure. They define:

- **Who thinks about what** (Ring 1 thinks about direction, Ring 2 thinks about coordination, Ring 3 thinks about building)
- **What kind of input each ring receives** (Ring 1 gets strategic context, Ring 2 gets Socratic briefs, Ring 3 gets directive briefs)
- **What authority each ring has** (Ring 1 sets direction, Ring 2 coordinates, Ring 3 executes, gates verify, observation feeds everyone)
- **How information flows** (up through Socratic briefs, out through directives, sideways through gates, everywhere through observation)

An agent arriving in MESA reads the governance core. They understand which ring they're in and what that means. They know how to receive input and what to do with it. They know who to communicate with and how. The architecture is self-documenting because it's embedded in how agents boot.

This is the thing that makes an agentic company coherent: not management meetings or hierarchical approval chains, but clear architecture built into the operating system. Agents don't have to guess how decisions get made. It's encoded. Agents don't have to wonder who owns what. It's defined by rings. Agents don't have to remember principles from three sessions ago. They read them every session.

The architecture is the system. The system is the governance. The governance is the company.

---

**MESA Framework — Concentric Rings Architecture**
Created in Redmond, Oregon
March 2026
