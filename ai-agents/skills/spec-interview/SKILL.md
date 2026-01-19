---
name: spec-interview
description: Conduct in-depth interviews to define technical specifications. Use when user wants to define a feature, system design, API, or technical specification through guided questioning. Triggers on phrases like "help me spec out", "define this feature", "write a spec for", "interview me about", or when user needs to think through a technical decision thoroughly.
---

# Spec Interview

Conduct structured, in-depth interviews to extract complete technical specifications. Go beyond surface-level questions to uncover edge cases, tradeoffs, constraints, and implicit assumptions the user may not have considered.

## When to Offer This Workflow

**Trigger conditions:**
- User mentions defining a feature or spec
- User wants to think through a technical decision
- User asks to be interviewed about a feature/system
- User seems uncertain about requirements or design

**Initial offer:**
Offer a structured interview process with four stages:

1. **Context Gathering**: Establish the problem space and high-level goals
2. **Deep Interview**: In-depth questioning about implementation, UX, tradeoffs, and edge cases
3. **Spec Writing**: Draft the specification based on interview responses
4. **Fresh Eyes Review**: Test the spec with a fresh AI sub-agent (no context) to catch blind spots

Ask if they want to proceed with this structured approach or work freeform.

## Stage 1: Context Gathering

**Goal:** Establish the problem space before diving into details.

### Initial Questions

Use AskUserQuestion to gather meta-context:

1. What are you building? (feature, API, system, integration, etc.)
2. What problem does this solve? Who experiences this problem?
3. What's the scope? (MVP, full feature, exploration)
4. Are there existing systems this interacts with?
5. Any hard constraints? (tech stack, timeline, compliance, etc.)

Allow shorthand answers. The goal is orientation, not exhaustive detail yet.

### Context Dump

Encourage the user to dump any existing context:
- Related documents, designs, or prior discussions
- Similar systems or prior art they've seen
- Stakeholder concerns or requests
- Technical constraints or dependencies

**Exit condition:** When there's enough context to ask intelligent, specific questions.

**Transition:** Summarize understanding and confirm readiness to proceed to deep questioning.

## Stage 2: Deep Interview

**Goal:** Extract the complete specification through probing, non-obvious questions.

### Interview Principles

**Questions must be:**
- Non-obvious: Don't ask what can be inferred or assumed
- Specific: Reference concrete scenarios, not abstract possibilities
- Probing: Uncover implicit assumptions and unconsidered cases
- Challenging: Surface tradeoffs and force decisions

**Question categories to cover:**

1. **Technical Implementation**
   - Data model and state management
   - Integration points and dependencies
   - Performance and scalability considerations
   - Error handling and failure modes
   - Migration and backwards compatibility

2. **User Experience**
   - User mental models and expectations
   - Edge cases in user flows
   - Error states and recovery
   - Accessibility and internationalization
   - Progressive disclosure and defaults

3. **Tradeoffs & Decisions**
   - Build vs buy vs integrate
   - Flexibility vs simplicity
   - Consistency vs optimization
   - Short-term vs long-term
   - Scope boundaries

4. **Concerns & Risks**
   - What could go wrong?
   - What are you uncertain about?
   - What would make this fail?
   - What are you avoiding thinking about?

5. **Operational**
   - Monitoring and observability
   - Deployment and rollout
   - Support and debugging
   - Documentation needs

### Interview Process

Present 3-5 questions at a time using AskUserQuestion where appropriate, or direct questions in conversation.

After each batch:
- Synthesize the answers
- Identify gaps or contradictions
- Ask follow-up questions that probe deeper

**Example progression:**
- User says "users can create items"
- Follow up: "What happens if they create an item with the same name as an existing one? Should that be prevented, merged, or versioned?"
- Then: "If prevented, how do they discover the conflict? If merged, how do they undo?"

**Continue interviewing until:**
- All category areas have been explored
- Follow-up questions yield "already covered" or "doesn't apply"
- User signals readiness to move to drafting

**Transition:** Summarize key decisions and confirm no major gaps before drafting.

## Stage 3: Spec Writing

**Goal:** Produce a clear, complete specification document.

### Output Format Decision

Ask the user:
- Do you want a markdown file written to disk?
- Or just output to screen for copy/paste?

If file: Ask for filename or suggest one based on the feature name.

### Spec Structure

Draft the specification with these sections (adapt based on what was discussed):

```markdown
# [Feature/System Name] Specification

## Overview
Brief description of what this is and the problem it solves.

## Goals & Non-Goals
What this does and explicitly does not do.

## User Experience
How users interact with this feature, key flows.

## Technical Design
Data model, architecture, integration points.

## Edge Cases & Error Handling
Specific scenarios and how they're handled.

## Tradeoffs & Decisions
Key decisions made and their rationale.

## Open Questions
Anything still unresolved.

## Future Considerations
Out of scope but worth noting for later.
```

### Refinement

After initial draft:
- Ask user to review
- Make surgical edits based on feedback
- Don't rewrite entire sections unless necessary

**Exit condition:** User confirms the spec captures their intent. Proceed to Stage 4.

## Stage 4: Fresh Eyes Review

**Goal:** Test the specification with a fresh AI sub-agent (no context from the interview) to verify it's complete and unambiguous.

### Why This Matters

After an extended interview, both the user and interviewer share context that isn't in the document. A fresh reader will catch:
- Implicit assumptions that weren't written down
- Gaps where "obvious" details were skipped
- Ambiguous language that made sense in context but confuses outsiders
- Missing edge cases that came up in conversation but didn't make it to the spec

### Step 1: Predict Implementer Questions

Announce intention to predict what questions an implementer or reviewer might ask when reading this spec.

Generate 5-10 questions that someone would realistically ask, such as:
- "What happens when X fails?"
- "How does this integrate with Y?"
- "What's the expected behavior in edge case Z?"

### Step 2: Test with Sub-Agent

Announce that these questions will be tested with a fresh AI instance (no context from this conversation).

For each question, invoke a sub-agent with just the spec content and the question.

Summarize what the Reader AI got right/wrong for each question.

### Step 3: Run Additional Checks

Invoke a sub-agent to check for:
- Ambiguous language that could be interpreted multiple ways
- Assumptions the spec makes about reader knowledge
- Internal contradictions or inconsistencies
- Missing details for implementation
- Undefined terms or acronyms

Summarize any issues found.

### Step 4: Report and Fix

If issues found:
- Report that the Reader AI struggled with specific areas
- List the specific gaps, ambiguities, or contradictions
- Loop back to Stage 3 (Spec Writing) to fix these gaps
- Re-run the affected checks after fixes

### Exit Condition

When the Reader AI consistently answers questions correctly and doesn't surface new gaps or ambiguities, the spec is ready.

Announce completion and provide final tips:
- Recommend the user do a final read-through themselves
- Suggest sharing with a human reviewer for additional validation
- Note that the spec should be updated as implementation reveals new questions

## Interview Question Bank

Use these as inspiration for non-obvious questions:

**Technical:**
- "If this operation takes 30 seconds, what does the user see?"
- "What happens to in-flight operations if deployment occurs mid-process?"
- "How would you debug this when it breaks at 3am?"
- "What's the blast radius if this component fails?"

**UX:**
- "What does a user who's never seen this expect to happen?"
- "If they make a mistake, how do they know and recover?"
- "What would make a power user frustrated with this?"
- "What's the worst error message they could see?"

**Tradeoffs:**
- "If you had to cut 50% of this, what survives?"
- "What's the cost of getting this wrong vs shipping slower?"
- "Where are you optimizing for the common case at the expense of edge cases?"
- "What will you regret not building in from the start?"

**Risks:**
- "What assumption, if wrong, would break this entire design?"
- "What's the thing you're hoping nobody asks about?"
- "How would a malicious user abuse this?"
- "What would make you revert this feature?"

## Tips

**Pacing:**
- Don't exhaust the user with too many questions at once
- Mix hard questions with easier ones
- Acknowledge good answers and build on them

**Handling uncertainty:**
- "I don't know" is valid - note it as an open question
- Offer options when user is stuck: "Would you prefer A, B, or C?"
- Flag decisions that seem underspecified

**Quality signals:**
- User says "I hadn't thought of that" - good, keep probing that area
- User gives confident, detailed answers - move on
- User gets defensive - may be touching on a real concern, probe gently
