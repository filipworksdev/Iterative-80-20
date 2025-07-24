# Iterative 80/20 Methodology

A streamlined approach for delivering maximum value quickly by focusing on the top ~20% of tasks that yield ~80% of the benefit. Rather than strict sprints or bulky ceremonies, this methodology revolves around a single recurring **Huddle** and a simple Kanban board. When tasks meet their “OK” threshold (roughly 80% completeness for essential value), they’re considered good enough to move on.

---

## Table of Contents
1.  [Overview](#overview)
2.  [Key Terms](#key-terms)
3.  [The Huddle](#the-huddle)
4.  [Scoring Items (RICE: Reach, Impact, Confidence, Effort, Value)](#scoring-items-rice-reach-impact-confidence-effort-value)
5.  [Kanban Flow & WIP Limits](#kanban-flow--wip-limits)
6.  [Definitions: “Definition of OK” & “Definition of Complete”](#definitions-definition-of-ok--definition-of-complete)
7.  [Milestones vs. Sprints](#milestones-vs-sprints)
8.  [Handling Dependencies](#handling-dependencies)
9.  [Managing Technical Debt](#managing-technical-debt)
10. [Tracker Items & Feature Lifecycle](#tracker-items--feature-lifecycle)
11. [Putting It All Together](#putting-it-all-together)
12. [Potential Pitfalls & Solutions](#potential-pitfalls--solutions)

---

## Overview

The Iterative 80/20 Methodology aims to deliver the majority of a project's value in a fraction of the time by zeroing in on high-impact, low-effort activities. Key principles:

* **80/20 Focus**: Concentrate on the small portion of work that yields most of the benefit.
* **Single “Huddle” Meeting**: Replace multiple ceremonies (refinement, planning, stand-ups) with a single, periodic meeting for re-prioritization and alignment.
* **Kanban Flow**: Track tasks on a simple board—Backlog, In Progress, Done—with continuous pull rather than time-boxed sprints, managed by clear Work In Progress (WIP) limits.
* **“OK” Threshold**: Each item is considered "OK" when it's about 80% complete for its essential value. The remaining work (the 20%) is explicitly managed as technical debt or follow-up tasks.
* **"Complete" Threshold**: Features are marked "Complete" when all associated work, including technical debt, is 100% finished.

---

## Key Terms

* **Huddle**: The single recurring meeting for backlog review, scoring, prioritization, and planning.
* **Definition of OK**: The criteria for an item to be considered 80% complete and ready to move to the next stage.
* **Definition of Complete**: The criteria for a feature (tracked by a Tracker item) to be 100% finished, including all associated technical debt and remaining work.
* **Tracker Item**: An optional, but recommended, overarching item used to group and track all related work items (development, design, research, technical debt, etc.) for a specific feature until it reaches 100% "Complete."
* **Value Score**: A metric derived from the RICE framework `(Reach x Impact x Confidence) / Effort` used to prioritize backlog items.
* **Iteration**: In the context of automatic technical debt value increase, an iteration is considered a **finished Tracker item**.
* **Work In Progress (WIP) Limit**: Rules defining the maximum number of items a developer or team can actively work on at any given time.

---

## The Huddle

The **Huddle** is the dynamic, central meeting of the Iterative 80/20 methodology, designed to be engaging, collaborative, and highly effective. It replaces multiple traditional agile ceremonies with a single, streamlined session focused on continuous prioritization, refinement, and flow. The Huddle is led by a **Huddlemaster** and incorporates a gamified **Funnel** process to ensure clear, team-driven RICE estimations.

Huddles should happen **regularly** (e.g., twice per work week, every Tuesday and Thursday at 10:00 AM) to maintain rhythm and predictability. Each Huddle ideally lasts around **60-90 minutes**, ensuring efficient, focused discussion.

### 1. The Huddlemaster (The Referee)

The **Huddlemaster** is a rotating facilitator responsible for running the Huddle session. This role is designed to be accessible to anyone on the team, including beginners, thanks to a clear checklist and structured process.

**Huddlemaster Responsibilities:**

* **Timebox Enforcer:** Uses a visual or audible timer (e.g., a bell or app) to announce transitions and ensure discussions don't drag on.
* **Spotlight Distributor:** Actively calls on quieter team members to ensure equal airtime and gently nudges overzealous talkers to wrap up.
* **Data Aggregator:** Summarizes key points and ensures final RICE scores and decisions are clearly noted after each item's discussion.
* **Conflict Mediator:** Guides the team through the "Estimation Obstacle" discussions, ensuring the process is followed collaboratively.
* **Retrospective Prompt:** Ends the session with a quick, time-boxed reflection (e.g., 60 seconds max): "What worked well in this Huddle? What might we try differently next time?"

**Tip:** A simple **"Huddlemaster Checklist"** (see below) should be posted visibly (e.g., on a wall or a shared digital page) to guide any Huddlemaster through their duties.

### 2. Three-Phase Huddle Flow

The Huddle is structured into three clear phases:

#### A. Pre-Huddle: Generation

* **Purpose:** To gather new items (features, bugs, ideas, research tasks, design elements, etc.) from all team members and stakeholders before the meeting.
* **What Happens:** Anyone can propose items. These should align with business needs and project plans. At this stage, only minimal detail is required, and no deep scoring is done yet. This phase ensures a broad spectrum of potential value sources.

#### B. In-Huddle: The Funnel Campaign

* **Purpose:** To discuss each proposed item in detail, assign or refine RICE scores collaboratively, and determine if it "survives" to the backlog or is "sent to the Graveyard of Ideas."
* **What Happens:**
    * The Huddlemaster starts a timer for each item (e.g., **30 minutes for small items, up to 1 hour for large/complex items**).
    * **Initial RICE Reveal:** Each team member privately determines their initial RICE scores (Reach, Impact, Confidence: 0.25, 0.5, 1, 2, 3; Effort: person-days). On the Huddlemaster's cue, all scores are revealed simultaneously. The Huddlemaster quickly identifies any significant differences.
    * **Running the "Estimation Obstacle" Funnel:**
        1.  **Raise an Obstacle:** The Huddlemaster asks if anyone has a strong objection to a specific RICE score component (e.g., "I think the Confidence score is too high," or "Effort seems too low").
        2.  **Collective Objection:** If **two or more people** share the same objection, an **"Estimation Obstacle" is raised** for that RICE component.
        3.  **Justify the Obstacle:** The Huddlemaster gives the individual(s) who raised the obstacle a brief time (e.g., 2-3 minutes) to explain their reasoning and provide context for their differing score.
        4.  **Team Vote on Validity:** After the explanation, the Huddlemaster facilitates a quick **team consensus check** (e.g., a show of hands) to see if the majority of the team **agrees or disagrees** with the presented objection.
        5.  **Resolve the Obstacle (The Outcome):**
            * **If the "Objection Stands" (Team Agrees):** The concern is confirmed. Everyone in the team whose initial score for that RICE component was *not* aligned with the objection must **adjust their score** to be closer to the objector's perspective. The Huddlemaster will then facilitate a quick re-evaluation or propose a **median/average** of these newly adjusted scores as the collective consensus for that RICE component. This ensures the item's estimate is updated based on collective wisdom.
            * **If the "Objection Doesn't Stand" (Team Disagrees):** The concern is not confirmed by the group. The individual(s) who raised the objection must **adjust their own scoring** for that specific RICE component to align more closely with the team's prevailing consensus. This means the item's estimate remains as initially proposed by the majority.
    * **Encounter Checks (Optional, can be integrated into Obstacles):** The Huddlemaster can also raise their own objections using encounters.
      1. Scope Beast - The item seems bigger than originally described.
         - Increase Effort by +1 or +2 steps if major complexity emerges.
      2. Knowledge Goblin - The team’s unsure about feasibility or has few references.
         - Decrease Confidence by 1 level (e.g., from 2 → 1).
      3. Synergy Bonus - The item complements existing or upcoming features.
         - Increase Impact by +1 if synergy is confirmed.
      4. Doubting Stakeholder - A key stakeholder or domain expert is not convinced.
         - Decrease Confidence by 1.
      5. Dependencies Hydra - External service, cross-team or legacy system is involved.
         - If easy to integrate, do nothing. If tricky, +1 or +2 to Effort.
      6. Excited Users - The team has data that users truly want this.
         - Increase Reach or Impact by +1 (team decides which).

    * **Value Calculation & Decision:** After all relevant obstacles are resolved, the item's final **Value Score** is calculated: `(Reach x Impact x Confidence) / Effort`. The team then decides if the item **"survives the Funnel"** (i.e., its value is high enough, and it's clear enough) and is placed in the prioritized backlog, or if it is **"sent to the Graveyard of Ideas"** for reconsideration later (e.g., if its value is below a predefined threshold, or if too many fundamental uncertainties remain). Items sent to the Graveyard are not deleted but parked for future potential resurrection.

#### C. Post-Huddle: Conclusion

* **Purpose:** To document final decisions and reflect briefly on the Huddle itself.
* **What Happens:** The Huddlemaster (or a delegated note-taker) updates the backlog tool with final RICE scores, notes on key discussions, and the item's "survived" or "graveyard" status. The session concludes with the Huddlemaster's quick retrospective prompt.

### 3. Huddlemaster Checklist (Example)

This checklist provides a step-by-step guide for any Huddlemaster to run an effective and engaging Huddle.

**Before the Huddle:**
* Review the list of proposed items (from the Pre-Huddle phase).
* Ensure the meeting space is ready (whiteboard, markers, timer, or digital tools).

**During the Huddle: Opening (First 5 minutes)**
1.  Welcome everyone and thank them for attending.
2.  Briefly state the Huddle's purpose: to prioritize and refine backlog items.
3.  Remind everyone of the timebox for the overall Huddle.
4.  Introduce the first item for discussion.

**During the Huddle: Per Item (Timebox: 5-20 minutes, depending on item size)**
1.  Start the timer for the item.
2.  Briefly present the item (1-2 minutes max).
3.  **Initial RICE Reveal:** Ask everyone to reveal their initial RICE scores (R, I, C, E).
4.  **Identify Discrepancies:** Note any significant differences in RICE scores that need discussion.
5.  **Facilitate "Estimation Obstacles":**
    * Ask: "Does anyone have a strong objection to a specific score (e.g., 'Confidence feels too high,' 'Effort too low')?"
    * If 2+ people agree, an "Estimation Obstacle" is raised.
    * Ask the objector(s) to explain their reasoning (2-3 minutes).
    * Ask the rest of the team: "Do you agree with this objection?" (show of hands/quick poll).
    * **If "Objection Stands":** "Okay, the team agrees. Everyone with a different score for [RICE component] must adjust their score to reflect this. What are your updated scores now?" Facilitate quick re-evaluation and propose median/average as consensus.
    * **If "Objection Doesn't Stand":** "The team doesn't agree with the objection. Objector(s), please adjust your [RICE component] score to align with the team's consensus."
6.  **Review Other Encounters (Optional/Integrated):** Briefly check if other common "Encounters" (Scope Beast, Knowledge Goblin, etc.) apply and lead a quick discussion/adjustment if needed.
7.  **Final Value Calculation:** Calculate the item's Value = $ ( \text{R} \times \text{I} \times \text{C} ) \div \text{E} $ using the final, agreed-upon RICE scores.
8.  **Decision on Survival:** Ask the team: "Based on this Value and our discussions, does this item 'survive the Funnel' and go to the backlog, or is it 'sent to the Graveyard of Ideas'?" Confirm the decision.
9.  Stop the timer for the item. Transition to the next item.

**During the Huddle: Closing (Last 2 minutes)**
1.  Briefly summarize items processed and decisions made.
2.  **Huddle Retrospective:** Ask: "What worked well in this Huddle? What might we try differently next time?" (1 minute max).
3.  Thank everyone and close the Huddle.

**After the Huddle:**
* Update the backlog tool with all final RICE scores, decisions, and notes.
* (Optional) Share brief Huddle summary/notes with the team.

---

## Scoring Items (RICE: Reach, Impact, Confidence, Effort, Value)

Each backlog item receives scores based on the **RICE framework** to determine its priority:

1.  **Reach (0.25, 0.5, 1, 2, 3)**
    * How many people or customers will this feature/item impact within a given timeframe (e.g., a month)?
    * *Examples:* 0.25 (few internal users), 3 (all customers).
2.  **Impact (0.25, 0.5, 1, 2, 3)**
    * How much will this feature/item contribute to the goal if it reaches those people?
    * *Examples:* 0.25 (minimal effect), 3 (significant boost to revenue or core KPI).
3.  **Confidence (0.25, 0.5, 1, 2, 3)**
    * How confident are we in our estimates for Reach, Impact, and Effort?
    * *Examples:* 0.25 (low confidence, many unknowns), 3 (high confidence, well-defined).
4.  **Effort (Person-Days)**
    * The total number of person-days required from all team members to complete the item to the "Definition of OK" threshold. This is a sum of individual estimates.
    * *Example:* 1 person-day, 5 person-days.

**Scoring Process**:
During the Huddle, each team member will independently provide an initial score (using a 1-5 level scale for R, I, C, and their estimate for Effort). If there's a difference of 2 or more levels between team members' scores for Reach, Impact, or Confidence, the team will discuss the item to align understanding and bring the scores closer (ideally within 1-2 levels difference) before producing the closest average level/score. For Effort, the team discusses and agrees on a collective person-day estimate.

**Value Score**:
The **Value Score** is calculated as: `(Reach x Impact x Confidence) / Effort`
Items are then sorted in the backlog from highest Value to lowest. Each item retains its calculated Value and Effort scores.

---

## Kanban Flow & WIP Limits

The Kanban board tracks items through a simple flow: **Backlog**, **In Progress**, **(In Testing - Optional)**, **Done**.

* **Continuous Pull**: Items are pulled from the Backlog into "In Progress" as capacity becomes available, always prioritizing the highest Value items.
* **Work In Progress (WIP) Limits**: To ensure focus and optimize flow, clear WIP limits are enforced at the individual developer level:
    * A developer can actively work on **1 to 3 items** with a combined **total effort of 10 person-days or less**.
    * Alternatively, a developer can work on **1 single item** if its **effort is greater than 10 person-days**.
    * A developer can only pull a new item into "In Progress" when one of their current items has been moved to "Done" (or "In Testing" if applicable) and has passed initial integration checks. The new item must also adhere to the 1-3 / >10 effort rule.
* **"In Testing" (Optional)**: This column can be used to explicitly track items that are undergoing dedicated quality assurance or user acceptance testing before being considered "Done" to their "Definition of OK" state.

---

## Definitions: “Definition of OK” & “Definition of Complete”

These two distinct definitions guide the lifecycle of work items and features:

1.  ### Definition of OK (80% Threshold)
    This defines when a backlog item (e.g., a user story, bug fix, or sub-task of a Tracker) is considered sufficient to move forward, delivering its core value quickly while acknowledging that further refinement might be needed.
    * **Criteria for "OK"**:
        * Core functionality is implemented and demonstrable.
        * Unit tests passed (where applicable).
        * Code is reviewed according to team standards.
        * No known critical defects or blockers.
        * Deployable to a staging or testing environment.
        * Acceptance criteria for the *core* functionality are met.
        * (Example: A login feature allows users to log in, but error message styling or password recovery links might be part of the remaining 20%).

    When an item meets its "Definition of OK," it can be moved to "Done" on the Kanban board. The remaining 20% of work (e.g., edge cases, polish, non-critical bugs, additional UI refinement) is identified and handled as new, separate backlog items, often linked to a "Tracker" or explicitly marked as technical debt.

2.  ### Definition of Complete (100% Threshold for a Feature)
    This defines when an entire feature (tracked by a **Tracker Item**) is considered 100% finished, including all its associated work, polish, and identified technical debt. This signifies that the full business value of the feature, as initially understood, has been achieved.
    * **Criteria for "Complete"**:
        * All backlog items associated with the Tracker item have reached their "Definition of OK."
        * All identified technical debt items specifically linked to this feature/Tracker have been resolved and completed.
        * All bugs or remaining issues identified during the 80% completion phase are addressed.
        * Integrated and tested end-to-end.
        * Ready for release to production (or already released).
        * Documentation, design artifacts, and other non-code elements are finalized.

    Once a Tracker item reaches "Definition of Complete," the iteration on that specific feature is done, and the Tracker is moved to "Done" on the Kanban board. Any future bugs or defects discovered post-completion will be added as new backlog items, outside the scope of the now "Complete" Tracker.

---

## Milestones vs. Sprints

In Iterative 80/20, we use **Milestones** instead of time-boxed Sprints.

* **Milestones**: A Milestone represents a significant project goal or a major deliverable. It includes a number of items that the team continues to implement until the Milestone is achieved. Milestones are outcome-oriented rather than time-boxed, allowing for flexibility in delivery based on value and effort.
* **No Sprints**: Unlike Scrum, there are no fixed-duration sprints. The team continuously pulls the highest-value items from the backlog, maintaining a constant flow of work. This enables faster delivery of value and quicker adaptation to changing priorities.

---

## Handling Dependencies

Dependencies are inevitable, but Iterative 80/20 provides a clear approach to minimize their impact:

* **Identification**: Dependencies are identified and discussed during the Huddle, ideally when an item is being scored.
* **Visualization**: Blocked items are clearly marked on the Kanban board (e.g., with a "Blocked" tag or color) and the blocker (if it's another item) is linked.
* **Skip and Prioritize**: If a high-value item (A) is blocked by a lower-value item (B), the team will skip item A and continue with other high-value items in the backlog.
* **Feature-Driven Unblocking**: Critically, if the blocking item (B) is part of the **same Tracker** as the high-value blocked item (A), or if solving B is crucial to unblock a very high-value Tracker, then item B's priority will be *elevated* to match the overall **Tracker's value**. This ensures that dependencies on high-priority features are addressed promptly, preventing long-term stalls.
* **Huddle Focus**: The Huddle dedicates time to reviewing all blocked items and actively seeking solutions to unblock them, potentially re-prioritizing the blocker or coordinating with external teams if necessary.

---

## Managing Technical Debt

Technical debt is explicitly acknowledged and managed in Iterative 80/20, rather than being ignored:

* **Creation**: When an item reaches its "Definition of OK" (80%), any identified remaining 20% of work, including polish, edge cases, non-critical bugs, or refactoring opportunities, is immediately captured as new, separate backlog items. These are explicitly tagged as "Technical Debt" or "Follow-up Work."
* **Re-evaluation**: These new technical debt items are brought to the next Huddle for evaluation and scoring using the RICE framework, just like any other backlog item.
* **Automatic Value Increase**: To prevent technical debt from being perpetually deferred, items clearly marked as "Technical Debt" will automatically increase their **Value Score by 0.25** after every **finished Tracker item (iteration)**. This mechanism naturally elevates their priority over time, forcing a re-evaluation and encouraging developers to address them.
* **Tracker Dependency**: For a **Tracker Item** to be considered "Complete" (100%), all technical debt items specifically identified and linked to that feature must also be completed. This ensures that features are polished and robust before being considered truly done.
* **Visibility**: Technical debt items are visible on the Kanban board, ensuring transparency and accountability.

---

## Tracker Items & Feature Lifecycle

**Tracker Items** are a core component of Iterative 80/20, providing a flexible and powerful way to manage the full lifecycle of complex features and initiatives. Their use is optional but highly recommended.

* **Purpose**: A Tracker item serves as an umbrella for all related work required to bring a feature from concept to 100% "Complete." This can span many individual backlog items and "iterations."
* **Value Calculation**: The Value Score of a Tracker item is dynamically calculated as the **average of the Value Scores of all its current sub-items** (both "OK" and "In Progress"). This ensures the Tracker's priority reflects the cumulative value of its components.
* **Lifecycle**:
    1.  **Creation**: A Tracker is typically created when a new, complex feature or business objective is identified.
    2.  **Sub-items**: As the feature is broken down, individual work items (development tasks, design, research, technical debt, bugs, etc.) are created and linked as sub-items to the Tracker.
    3.  **Progression**: Individual sub-items are processed through the Kanban flow, reaching their "Definition of OK."
    4.  **Completion**: The Tracker itself moves to "Done" only when all its sub-items, including all associated technical debt and remaining work, meet the "Definition of Complete" criteria. At this point, the feature is considered 100% finalized in its current form.
* **Shared Ownership**: Tracker items can be worked on by multiple developers and teams simultaneously, tracking the overall effort and progress for the feature.
* **Flexibility**: Tracker items are not limited to just development tasks. They can encompass any activity that contributes value or helps meet business needs, including:
    * **Learning & Research**: Items for team members to acquire new skills or investigate solutions.
    * **Proof of Concepts (PoCs)**: Spikes or small experiments to validate assumptions.
    * **Art & Design**: UI/UX design, graphic assets.
    * **Market Research & User Adoption**: Activities to understand user needs, test market fit, or track post-release success metrics (e.g., user engagement, business value realization, feedback integration).
    * **Experimentation**: Running A/B tests or other experiments.

This flexibility allows the methodology to be applied to a wider range of projects, ensuring that all valuable work, not just coding, is visible, prioritized, and tracked.

---

## Putting It All Together

The Iterative 80/20 Methodology combines continuous flow with smart prioritization and explicit debt management. The team continuously pulls the highest-value items from a prioritized backlog. Items move through "In Progress" to "Done" once they meet the "Definition of OK." Any remaining 20% of work is captured as new tickets, potentially increasing in priority over time if it's technical debt. Complex features are managed end-to-end via flexible "Tracker" items, which only achieve "Complete" status when all work, including debt, is done. The regular "Huddle" acts as the central hub for team alignment, prioritization, and dependency resolution, driving continuous delivery of value.

---

## Potential Pitfalls & Solutions

Even with a streamlined approach, certain challenges can arise. Proactive identification and solutions help maintain flow and effectiveness.

* **Pitfall 1: Accumulation of "Remaining 20%" (Technical Debt)**
    * **Issue**: If the 20% of work identified after "Definition of OK" is constantly deferred or new technical debt is never prioritized, it can lead to a brittle, unmaintainable product.
    * **Solution**: The automatic value increase for technical debt items forces re-evaluation. Additionally, the "Definition of Complete" for a Tracker requires all associated technical debt to be resolved, providing a strong incentive to address it. Regularly (e.g., once a month or quarter), dedicate a portion of the Huddle to specifically reviewing the *amount* and *impact* of accumulating technical debt, and consciously allocate time to it.
* **Pitfall 2: Overly Subjective RICE Scoring**
    * **Issue**: Without clear guidelines, team members' interpretation of Reach, Impact, and Confidence scores (0.25-3) can vary wildly, leading to inconsistent prioritization.
    * **Solution**: Invest time in defining clear examples for each RICE score level (e.g., what does "Impact = 3" truly mean for your specific product/business?). Regularly (e.g., quarterly) conduct calibration sessions where the team scores a set of known, completed items to align their understanding. The "2+ level difference" discussion in the Huddle is also a built-in calibration mechanism.
* **Pitfall 3: "Huddle" Becomes Too Long or Unfocused**
    * **Issue**: Combining multiple agile ceremonies into one "Huddle" can lead to a lengthy, chaotic meeting if not managed well.
    * **Solution**: Assign a rotating **Huddle Facilitator** whose primary role is to keep the meeting time-boxed (e.g., 60-90 minutes), focused on the agenda, and ensure all team members contribute. Establish a clear agenda for each Huddle (as defined above). Consider using a "parking lot" for tangential discussions to be addressed separately.
* **Pitfall 4: Unmanaged Dependencies Becoming Bottlenecks**
    * **Issue**: While the "skip and prioritize" rule helps, if blockers are not actively addressed or if external dependencies are chronic, flow can still grind to a halt.
    * **Solution**: Ensure blocked items are highly visible on the Kanban board with clear reasons. The Huddle must dedicate explicit time to reviewing and actively working to resolve blockers, leveraging the "feature-driven unblocking" rule. For external dependencies, a designated person (e.g., a "Flow Manager" or team lead) might need to actively communicate and coordinate with external teams to resolve them.
* **Pitfall 5: Inconsistent "Definition of OK" Across Items/Teams**
    * **Issue**: If the criteria for "OK" are vague or interpreted differently, it can lead to inconsistent quality, more rework, or hidden debt.
    * **Solution**: The "Definition of OK" needs to be a **team-agreed, explicit, and visible checklist**. It should be reviewed and refined periodically (e.g., every few months or after a major milestone) by the entire team to ensure it remains relevant and effective.
* **Pitfall 6: Loss of Big Picture (for individual items)**
    * **Issue**: With a focus on 80% completeness and continuous flow, individual developers might lose sight of how their specific item contributes to the larger feature or project goal.
    * **Solution**: The **Tracker item** is key here. Ensure individual backlog items are clearly linked to their parent Tracker. During the Huddle, when discussing items, briefly remind the team of the larger Tracker context. Encourage developers to look at the overall Kanban board to see the flow of all work.
