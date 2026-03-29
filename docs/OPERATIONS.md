# OPERATIONS.md — MESA Self-Sustaining Mechanisms

MESA is designed to run without constant human intervention. The operational mechanisms are self-sustaining. This document covers how.

If you're reading this, you already understand that an agentic company looks different from a human one. MESA's agents don't carry knowledge between sessions. They read everything they know from files at the start of every session. That single principle — the files are the memory — drives every operational design decision. The governance files are not documentation. They are the company's brain.

What that means operationally is that every correction makes every agent smarter immediately because they all read the same files. An agent arriving on day one has the same institutional knowledge as an agent that's been running for months. The system compounds knowledge automatically, if you design the mechanism right.

This document covers the mechanisms that make that happen.

---

## Mechanical Over Behavioral

This was one of the hardest lessons in building MESA.

Behavioral guidelines fail under exactly the conditions that cause problems. "Remember to check the governance files before editing" fails when the session is long, momentum is building, and the work feels natural. The agent who's drifting is the worst judge of whether it's drifting.

A checkpoint that depends on remembering isn't a checkpoint. It's a hope.

MESA uses a four-question test for every proposed checkpoint. If the answer to any question is no, the checkpoint gets redesigned until it's mechanical.

1. **Is it automatic?** Does it fire without the agent choosing to invoke it?
2. **Does it hold under momentum?** Would it still work at hour three of an intense build session?
3. **Does it have a specific trigger?** Is there an unambiguous event that activates it?
4. **Does it produce an artifact?** Is there proof it ran — a file, a log entry, a database record?

Why this matters operationally: behavioral checkpoints get converted or removed. Always. The governance stack only contains constraints that will actually constrain, regardless of whether anyone is paying attention.

Examples of what this eliminates:
- "Check the charter before starting" → Replaced with mandatory charter read at session boot (automatic, specific trigger: session start, produces: structured context window state).
- "Remember to flag ambiguity" → Replaced with a reflection template that executors complete at handoff (automatic, produces: reflection artifact).
- "Be consistent with previous decisions" → Replaced with decision log searches triggered at specification time (automatic, produces: lookup results).

The principle applies to every operational mechanism in MESA. The system works whether or not anyone is watching. That's the design requirement.

---

## The Learning Flywheel

This is the core of MESA's self-sustaining design. It solves a hard problem: how do you compound knowledge without compounding governance weight?

The original design said every correction becomes a permanent addition to the governance stack. That worked during building — the system accumulated institutional knowledge fast. But it has no natural stopping point. The stack grows on every session, every correction, every finding. Eventually the governance becomes too large for agents to hold in context.

The mature design separates immediate fixes from permanent knowledge. It's a four-step cycle that runs continuously:

### Step One: Fix Immediately, Always

Every correction gets applied the moment it's identified. The three-occurrence threshold governs permanent codification, not immediate response.

If an agent makes an error in classification, the correction applies instantly to the current work. If a builder misunderstands a requirement, the clarification gets logged and the work continues. If a gate finds a quality issue, it blocks and gets fixed before proceeding. The system doesn't wait for pattern evidence to fix problems. Single corrections are incidents. Patterns are institutional knowledge.

### Step Two: Log Everything

Builders reflect at the end of every handoff with structured fields:
- **Friction**: What caused hesitation or backtracking?
- **Surprise**: What behaved differently than expected?
- **Pattern candidate**: If this happened three more times, what should change?

Corrections are logged with causal categories. Health check findings are tracked with date and type. Every session produces a structured reflection artifact.

The reflection template is non-optional. It's part of the session structure. It produces evidence. That evidence feeds the flywheel.

### Step Three: Identify Patterns Weekly

A dedicated agent synthesizes all reflections, corrections, and health check findings into a weekly digest. The digest identifies patterns — recurring friction points, repeated surprises, categories of findings that keep appearing.

The synthesis agent doesn't filter. It looks at volume and recurrence. When the same type of finding appears three times within a defined window (usually a 30-day lookback), it surfaces as a pattern candidate.

The digest is mechanical and happens on a fixed schedule. The system doesn't wait for someone to decide to look. The digest runs every Friday regardless of whether anyone reads it.

### Step Four: Three Occurrences Earn Permanence

When the same type of finding appears three times within the pattern window, it becomes a candidate for the playbook. The orchestration layer proposes the addition. The owner approves. One occurrence is a fix. Two is a note. Three is a pattern that earns institutional knowledge.

This creates a natural governor on governance growth. Permanent additions require evidence. The system stops accumulating marginal rules. It codifies patterns.

### The Flywheel Effect

Here's what makes this self-sustaining: **the system gets smarter every week whether or not anyone is watching.**

The flywheel runs automatically. No one has to remember to synthesize. No one has to decide whether something matters. The digest happens on a fixed day. Patterns are identified by recurrence, not by judgment. The governance stack only grows when growth is earned by pattern evidence.

An agent arriving in month three of operation reads a governance stack that has been distilled through three months of real work, real corrections, and real patterns. The agent doesn't get a bloated early-draft version of the rules. It gets the version that has been tested by experience.

This is how institutional knowledge compounds in an agentic system. Not through ambitious rulemaking. Through evidence-driven permanence.

---

## Session Structure

A MESA session is not open-ended. It has a defined flow. The structure itself is mechanical — not optional.

### Boot

The session starts here. The agent reads governance in priority order (Structure First):

1. OWNER.yaml — How the founder actually thinks
2. CHARTER.md — Scope and authority for this agent
3. PLAYBOOK.md — Operational standards and checkpoints
4. CONTEXT.md — Current state, active projects, decision log

This reading takes precedence. Nothing else happens until the governance is in context. The session skeleton is already filled before the work starts.

### Brief

The agent receives a task. It's either Socratic or Directive, depending on the agent's role:

- **Socratic brief** (decision-makers): The problem, context, and a request for independent reasoning. The sender's proposed solution comes after the agent has thought it through. The best version of both becomes the recommendation.
- **Directive brief** (executors): Clear instructions, all required inputs, spec to build within. When something is ambiguous, the executor stops and flags rather than assumes.

The brief references governance entries by line and section so the agent can look up the exact text if needed.

### Execute

The agent works within the charter. It follows the playbook. It produces output — code, analysis, decision, artifact.

Execution is not free-form. It's bounded by spec, governed by checkpoints, and constrained by the four-question test. Ambiguity gets flagged. Drift gets surfaced. Work proceeds.

### Reflect

At the end of the handoff, the agent completes the reflection template:

```
Session: [ID]
Agent: [Name]
Task: [Brief description]

Friction: [What caused hesitation or backtracking?]
Surprise: [What behaved differently than expected?]
Pattern candidate: [If this happened three more times, what should change?]

Corrections: [List any corrections applied, with brief explanation]
Decisions: [List any decisions made, with brief explanation]
State updates: [List any updates to CONTEXT.md, decision log, or playbook]
```

The reflection is logged automatically. It becomes part of the digest input.

### Log

Corrections, decisions, and state updates are recorded in the decision log. The log entry references the session and includes:

- Date and time
- Finding or correction
- Category (governance, spec, implementation, dependency, risk)
- Status (applied, pending, candidate for pattern)
- Occurrences (tracked for pattern evidence)

The log is not for narrative. It's for data. It feeds pattern analysis.

---

## Health Checks and Drift Detection

The observation layer (Ring 5) is the nervous system. It tracks everything continuously. It detects drift without anyone choosing to invoke detection.

### Continuous Tracking

Health checks run on fixed schedules. They produce structured results. Examples:

- **Governance currency**: Does the charter match actual authority? Are decision log entries properly categorized? Are reflection logs complete?
- **Specification adherence**: Did execution follow spec? Were deviations documented?
- **Checkpoint function**: Did gates fire when required? Did corrections get logged?
- **Authority boundaries**: Are orchestration and execution decisions properly separated? Is authority flowing inward as designed?
- **Pattern emergence**: Are new patterns visible in the digest? Are three-occurrence thresholds being crossed?

Each check produces a structured result: pass, warning, or fail. The result goes to the health log with timestamp, category, and severity.

### Fixed Schedules

The checks run on a schedule, not on demand:

- **Hourly**: Checkpoint function, specification adherence (sample basis)
- **Daily**: Governance currency, decision log completeness
- **Weekly**: Authority boundaries, pattern emergence, overall system health
- **Monthly**: Deep governance audit, drift detection across rings

Nothing depends on someone remembering to check. The checks fire automatically.

### Drift Detection That Runs Automatically

Drift is deviation from principle. It happens slowly. It's easy to miss in the moment. It compounds.

MESA's drift detection watches for specific patterns:

- **Governance drift**: Rules being applied inconsistently, or rules being ignored under pressure
- **Authority drift**: Decisions being made at the wrong ring, or authority boundaries being crossed
- **Scope drift**: Work extending beyond charter, or charter growing without approval
- **Context drift**: Session momentum carrying an agent beyond documented intention
- **Pattern drift**: Corrections being made but not logged, or logs not feeding the digest

When drift is detected, the alert is immediate. It goes to the orchestration layer. The orchestration layer either corrects the drift in real time or escalates to the owner.

Drift detection produces artifacts: the specific evidence that drift occurred, the magnitude of the drift, and the recommended correction. The artifact goes into the decision log. It feeds pattern analysis.

---

## The Corrections Log

The corrections log is the operational record of how the system learns.

### Format

Each log entry captures:

```
Date: [YYYY-MM-DD HH:MM]
Finding: [What was wrong?]
Correction: [What changed?]
Category: [governance | spec | implementation | dependency | risk | process]
Session: [Session ID where correction occurred]
Occurrences: [1, 2, 3, or more within pattern window]
Status: [applied | pending | candidate for permanence]
```

### Purpose

The log is operational intelligence. It shows:

- Where the system is failing (concentrated in certain categories)
- Whether the same problems recur (pattern evidence)
- What corrections are actually working (fixes that reduce recurrence)
- When to escalate (drift or high-frequency failures)
- When to make permanent additions to governance (three-occurrence threshold)

The log doesn't exist to document what went wrong. It exists to feed pattern analysis and to make future corrections visible to agents who read the governance files.

### Why Categories Matter

Categories enable pattern detection. "We had three specification issues" is less actionable than "we had three specification issues, all in the ambiguity subcategory, all in the same domain."

The category system is:

- **Governance**: Misalignment between what's written and what's intended
- **Spec**: Ambiguity or incompleteness in the brief or task definition
- **Implementation**: Execution diverging from spec or charter
- **Dependency**: Upstream work not ready, or blocked on external input
- **Risk**: Unintended consequence, security issue, or escalation required
- **Process**: Session flow, reflection, or logging mechanics not working

When a pattern emerges in a specific subcategory, the permanent addition targets that subcategory specifically. The playbook grows precise because the evidence is precise.

### Why Occurrences Are Tracked

A correction without evidence is an opinion. Three corrections of the same type within a pattern window is a pattern. The occurrence count is the evidence.

The pattern window is typically 30 days. If the same correction has been applied three times within the last 30 days, the pattern candidate is ready for owner approval and permanent addition.

Tracking occurrences also shows decay. If a correction hasn't recurred in 30 days, the system can assume the fix held. If it recurs after 30 days, it's a separate pattern signal.

---

## Governance Reviews

Governance doesn't evolve haphazardly. It evolves on a structured schedule. Each review cadence serves a different purpose.

### Daily Brief

**When**: Every morning or at the start of the operational day
**Who**: Orchestration layer, observation layer
**What**: Five-minute summary of the previous day's findings

- Corrections applied (by category)
- Checkpoints that fired
- Drift alerts
- Escalations or risks that need visibility

The brief is scanning. It produces a health snapshot and flags anything that requires attention before the day starts. It's operational temperature-taking.

### Weekly Deep

**When**: End of week (Friday or Sunday, fixed)
**Who**: Orchestration layer, pattern synthesis agent, owner
**What**: Pattern analysis and proposed permanence

- Digest of all reflections and corrections
- Pattern candidates (findings that crossed three-occurrence threshold)
- Proposed additions to playbook
- Trend analysis (is drift increasing, decreasing, shifting categories?)

The owner reviews the digest and approves permanence candidates. This is where the learning flywheel turns. Patterns become institutional knowledge.

### Monthly Full

**When**: Last Friday of the month, fixed
**Who**: Owner, orchestration layer, strategic advisor (if present)
**What**: Comprehensive governance health review

- Governance stack size and weight (are agents able to hold it in context?)
- Redundancy or overlap in rules
- Rules that haven't surfaced in corrections (are they still needed?)
- Authority boundaries and cross-ring alignment
- Overall system alignment with intent

The monthly review is where consolidation happens. If rules can be merged. If categories can be simplified. If the stack is growing faster than institutional learning justifies.

### When to Escalate

Escalation is not optional when:

- **Authority has drifted across ring boundaries** (a builder making decisions, or orchestration overriding execution without spec change)
- **The same correction has been applied five times** (pattern is clear, but the permanent fix isn't holding, or the fix wasn't permanent)
- **Governance is governing itself instead of the product** (the stack is growing, rules are about rules, agents are spending time interpreting rather than executing)
- **A checkpoint failed to fire** (a mechanical check broke, or something that should be automatic has become manual)
- **Correction velocity is increasing** (more corrections per session, suggesting systemic misalignment)

When escalation occurs, the owner is briefed with the specific evidence. The escalation produces a decision. The decision updates the governance or resets the system alignment. Escalation is a correction at the governance level.

### The Signal for Phase Transition

MESA has natural lifecycle phases: Building → Consolidation → Freeze → Maintenance.

The signal to transition from Building to Consolidation is when **the governance starts governing itself instead of governing the product.**

You'll see it:
- Rules about rules (meta-governance growth)
- Agents spending more time interpreting governance than executing work
- Corrections becoming about rule clarity rather than operational problems
- The digest identifying patterns in pattern identification, rather than product patterns

When that happens, it's consolidation time. Reduce. Merge. Freeze. The system is ready.

---

## The System Works Because It's Designed To

MESA's operational mechanisms are not guidelines. They are mechanical constraints that function whether or not anyone is paying attention.

- **Corrections log automatically.** It's part of the session structure.
- **Patterns surface weekly.** The digest runs on a fixed schedule.
- **Governance grows on evidence.** Three occurrences is the threshold, not discretion.
- **Checks fire continuously.** Health checks and drift detection don't require invocation.
- **Sessions start the same way.** Charter read, governance in context, scope defined.
- **The flywheel turns.** Whether the owner is watching or not.

This is what it means to design for sustainability. The system doesn't depend on people remembering. It depends on mechanisms that work whether or not anyone is paying attention. That's how you run a company on AI agents. That's how you stay aligned when the team doesn't carry institutional memory between sessions. You build alignment into the file system. You make learning automatic. You make the constraints mechanical.

An agent arriving to run a build session on day one reads the same governance as one running on month six because the governance was refined by real work, real corrections, and real patterns over those six months. The system compounds knowledge. It does this automatically.

That's MESA operations.
