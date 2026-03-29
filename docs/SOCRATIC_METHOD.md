# SOCRATIC_METHOD.md — Two Brief Types. One Principle: Match Form to Role.

**Elevated thinking. Solid ground.**

---

## The Opening

MESA doesn't use one communication pattern. It uses two. Not because we like variety. Because the pattern that works for a decision-maker fails catastrophically for an executor, and vice versa.

This distinction matters more than it sounds. Get it right, and your orchestration layer thinks independently and your builders execute reliably. Get it wrong, and your decision-makers become order-followers while your builders spiral in analysis paralysis.

The pattern doesn't depend on the sender's preference. It depends on the receiver's role.

---

## The Problem This Solves

Early in MESA, everyone got the same thing: directives. The founder would make a decision and send it to the orchestration layer — COO, CTO — with clear instructions: build it this way, in this order, for these reasons. Execute.

The agents executed. But something was broken about it.

The founder started noticing that the orchestration layer kept pointing out flaws. The CTO would say: "I see what you're building, but you're not accounting for the fact that our data model makes this pattern slower than you think." The COO would say: "I see the priority you've set, but I know the execution layer is working on a blocker you didn't see last session."

These weren't insubordinate comments. These were insights from people closer to the work than the founder was. But they were being delivered as corrections to already-decided plans, not as input into the decision.

Meanwhile, at the build layer, the opposite problem was happening. Builders were getting Socratic briefs — questions, context, "what do you think?" — when what they actually needed was a specification. Builders would overthink the architectural implications of a directive that had already been decided. They'd second-guess the prioritization. They'd end up slower and less confident because they were being asked to reason through something that had already been reasoned through.

Both layers suffered because the brief type was mismatched to the role.

The founder was using directives to prevent chaos. The builders needed clear specs. But the choice cost the orchestration layer their thinking.

---

## Socratic Briefs — For Decision-Makers

**Who receives them:** The orchestration layer. COO and CTO. Ring 2. Agents whose job is to make architectural and operational decisions, not to execute within a spec.

### The Three-Section Structure

A Socratic brief has three sections, delivered in a specific sequence:

**Section 1: The Problem**

The sender presents the situation. Not the solution. The situation.

"We're at the point where manual deployment is taking too long. Our deployment cycle is twelve hours. We need architectural guidance: do we build CI/CD in-house, use a third-party service, or hybrid approach? This affects infrastructure costs, team time, and how fast we can iterate."

That's it. The problem is presented. The decision-maker is asked: "What do you see here? What questions does this raise? What approach would you take if it were entirely your call?"

The decision-maker reasons independently. They form their own assessment based on what they know about the system, the team, the constraints. They think. They don't jump to the sender's conclusion.

**Section 2: Our Thinking**

Only after the decision-maker has reasoned independently does the sender reveal their thinking.

"We've been leaning toward a third-party service because we're not operating at infrastructure scale yet and we don't have a DevOps person. We think outsourcing this unblocks the team to build product features instead of infrastructure."

Notice what's not here: "You should do this." It's "Here's what we think. Here's why."

**Section 3: Learning Log**

The brief includes where this decision originated. What problem prompted the brief? What pattern was observed?

"This came up because deployment became a blocker on the last release. The team waited 8 hours for a deployment that should have taken 30 minutes. It's happened twice in the last month. We're logging this as a recurring infrastructure friction point."

This provides context. It shows the decision-maker the evidence that prompted the sender's thinking, not just the conclusion.

### Why This Works

The agent closest to the work — the CTO managing the entire architecture, the COO coordinating all the teams — often sees things the sender can't. They see integration patterns the sender missed. They see resource constraints that matter more than the sender realized. They see second-order effects.

A directive would suppress that knowledge. The decision-maker would follow the order and miss the opportunity to surface their own insight.

The Socratic method surfaces it.

When the CTO reasons independently, they might conclude: "A third-party service makes sense for now, but we need to plan the in-house transition for when we hit scale, because the vendor's API has limits that will bite us at 10x growth." That's stronger thinking than either the sender or the CTO alone could produce.

Or they might say: "Actually, I think we should build in-house. Here's why — our data model makes the standard deployment patterns inefficient, and a vendor won't understand that for months."

The sender now has insight they didn't have. The decision-maker's reasoning combines with the sender's to produce a recommendation that's better than either perspective alone.

This is why Socratic briefs go to decision-makers. They need to think. And the system needs the benefit of their thinking.

---

## Directive Briefs — For Executors

**Who receives them:** The execution layer. Builders. Ring 3. Agents whose job is to build within a specification that's already been decided and reasoned through.

### The Structure

A directive brief is simple: Clear instructions with all required inputs. What to build. Why it matters. The spec. Constraints. Definition of done.

Subject: **Implement CI/CD Pipeline**

**Why This Matters**

Deployment is currently a 12-hour manual process. This is our biggest blocker on iteration speed. Implementing CI/CD cuts deployment to 15 minutes, which unblocks product iteration and reduces deployment risk through automation.

**The Spec**

- Trigger: Automatically on commits to main branch
- Build stage: Run test suite, check code coverage (min 80%), run security scan
- Deploy stage: Stage to production, run smoke tests, deploy if all tests pass
- Rollback: Automatic rollback if deployed version fails health check in first 5 minutes
- Monitoring: Log all deployments, track deployment success rate, alert on failures
- Success criteria: All CI/CD stages pass. Deployment completes in under 15 minutes. No manual intervention required.

**Constraints**

- Must integrate with our existing GitHub repository
- Must work with our current authentication system (don't redesign auth)
- Must complete within two weeks

**Definition of Done**

- [ ] All CI/CD stages configured and tested
- [ ] Documentation written for the team on how to use the pipeline
- [ ] Dry run deployment successful
- [ ] Security team has signed off on the pipeline before production use

**Flag Ambiguity Rather Than Assume**

If anything in the spec is unclear — what "smoke tests" means in our context, what the rollback criteria should actually be, whether you should configure alerting now or wait for a separate work item — flag it and wait for clarification. Don't assume.

That's the directive. The thinking is done. The decision is made. The executor's job is to build it, flag ambiguity, and deliver it within spec.

### Why This Works

The thinking has already been done by the decision-maker. The orchestration layer has decided that CI/CD is the right move, reasoned through what approach makes sense, and produced a specification.

If you send a Socratic brief to an executor — "Here's our deployment problem, what do you think?" — the executor ends up in analysis paralysis. They start reasoning about architectural choices. "Should we use GitHub Actions or Jenkins? What about cloud-native approaches? What if we redesigned deployment around containers?"

This is death by overthinking. The executor becomes slower and less confident. They're re-reasoning decisions that were already made. They're adding cognitive load to a task that should be straightforward.

What executors need is clarity. Here's the spec. Build it. If something's ambiguous, ask. This removes friction and produces reliable execution.

---

## How to Choose

The decision is simple: Is the receiver a decision-maker or an executor?

**Decision-maker** (Ring 2 — orchestration layer):
- Making architectural choices
- Evaluating options
- Deciding what gets built in what order
- Resolving conflicts between departments
- **Brief type: Socratic**

**Executor** (Ring 3 — execution layer):
- Building within a specification
- Implementing a decided approach
- Delivering against a spec
- Flagging ambiguity, not resolving it
- **Brief type: Directive**

**Special case: Gates** (Ring 4 — verification layer):
- Gates answer to standards, not to briefs
- A gate doesn't receive either type of brief
- A gate runs a verification process and produces a pass/fail result
- The result can't be overridden except by the owner
- Gates are neither Socratic nor directive — they're deterministic

The ring determines the brief type. Don't overthink it beyond that.

---

## The Synthesis Step

In a Socratic brief, something important happens after both the decision-maker and the sender have reasoned independently.

The decision-maker has arrived at their own conclusion. The sender has revealed their thinking. Now they compare.

Where they align — that's high confidence. "The CTO thinks we should use a third-party service, and that's what I was going to recommend. Good. We're both seeing the same landscape."

Where they differ — that's a deeper reasoning opportunity. "The CTO thinks we should build in-house for architectural reasons, but I was thinking we should outsource to move faster. Let's dig into what the CTO is seeing that I missed."

The best version of both becomes the recommendation.

This is why the Socratic structure is sequential. If you revealed your thinking first, the decision-maker would anchor on it. Their independent reasoning would be influenced by what you said. The value of their separate perspective would be diluted.

By asking them to reason first, then showing your thinking, you get the full benefit of both. The synthesis is richer.

---

## What Goes Wrong When You Mix Them Up

**Decision-maker gets a directive:**

The CTO receives: "Here's what we're building. Build it in this order with this architecture. Execute."

The CTO has insights about why that architecture will create problems downstream. But the directive frames it as already-decided. The CTO becomes an order-follower instead of a thinking partner. Their knowledge goes unused. The decision gets executed well but in the wrong direction.

Over time, the decision-makers stop thinking. They follow orders. The organization loses the benefit of having orchestration agents who are close to the work.

**Executor gets a Socratic brief:**

The backend builder receives: "We need to scale the authentication system. What do you think? Here are some options. How would you approach it?"

The builder starts reasoning through architectural options. "Should we use OAuth? Should we redesign the token model? What if we..." The builder gets lost in analysis when they should be building. They produce work slower. They second-guess the decision because they're still reasoning about whether the decision was right.

Over time, builders become less decisive. They add too much thinking to execution. You wanted a 2-week implementation. You got a month of architectural deliberation.

Both are wrong. Match the brief type to the role.

---

## Three Examples in Practice

### Example 1: Socratic Brief to the CTO (Decision-Maker)

**Subject: Where Should We Put Data Storage?**

**The Problem**

We're going to be handling more user data soon. Our current setup has everything in one database. That works today, but we need to think ahead: Do we partition within one database? Do we distribute across multiple databases? Do we use a managed service? Each approach has different cost, complexity, and scaling implications.

Before you read our thinking: What does the architecture look like under each approach? What breaks first as we scale? What matters most to you in this decision?

[CTO reasons independently for a day or two.]

**Our Thinking**

We've been thinking we should stick with one database as long as possible because distributed systems are complex. But you know our usage patterns better than we do. If you're seeing reasons we'd hit limits sooner, that changes everything.

[CTO and sender synthesize. Better decision emerges.]

---

### Example 2: Directive Brief to a Backend Builder (Executor)

**Subject: Implement User Authentication Endpoint**

**Why This Matters**

We can't ship the product without authentication. Users need to log in. This is a hard blocker on everything else.

**The Spec**

- Endpoint: `POST /auth/login`
- Input: email, password
- Output: JWT token (valid for 7 days), user ID, user name
- Rate limiting: 5 failed attempts per IP per hour (after 5 failures, that IP is blocked for 1 hour)
- Error handling: Return specific errors (invalid email format, user not found, password incorrect, too many attempts)
- Test coverage: Unit tests for all code paths, integration tests for the endpoint, security tests for rate limiting
- Security: Must pass the security audit before deployment

**Constraints**

- Must integrate with the existing user database schema
- Must use the JWT library we're already using
- Must complete in 5 days

**Definition of Done**

- All code paths tested and passing
- Security audit completed and passed
- Rate limiting verified with load testing
- Documentation updated with the endpoint spec

Build this. If anything is ambiguous, ask. Don't assume.

---

### Example 3: Socratic Brief to the COO (Decision-Maker)

**Subject: How Should We Prioritize This Sprint?**

**The Problem**

We have three major work streams competing for the same builders: feature work on the product, infrastructure debt we've been deferring, and a customer integration that's time-sensitive. We can't do all three in the next four weeks. We have to choose.

What do you see from the operations side? Which of these actually unblocks the most downstream work? What's the hidden cost of deferring each one?

[COO thinks through the implications.]

**Our Thinking**

From the product side, I want to do the feature work because it's what we're selling. But I suspect you're seeing that infrastructure debt is actually the blocker on the next phase. Is that right?

[COO and founder synthesize priorities.]

---

## The Decision Framework in One Sentence

**If they're deciding: Socratic. If they're building: Directive.**

That's it. Everything else follows from this one principle.

---

## Closing: Why This Matters

Communication patterns shape how people think. A directive says "here's what to do." A Socratic brief says "here's the problem, what do you see?"

When you send a directive to a decision-maker, you're saying "I trust you to follow orders." When you send a Socratic brief to a builder, you're saying "I trust you to reason about something that's already been decided."

Both are ways of not trusting people with their actual role.

The Socratic method respects that decision-makers are thinking partners. They're closest to the work. They should contribute their perspective. Directive briefs respect that executors are specialists in reliable implementation. They should focus on building, not re-reasoning the decision.

Get the brief type right, and both layers work better. Decision-makers think. Builders build. The organization gets both better decisions and more reliable execution.

---

**MESA Framework**
Created in Redmond, Oregon
March 2026
By Phillip Austin
