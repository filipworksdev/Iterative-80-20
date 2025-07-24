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
* **Value Score**: A metric derived from the RICE framework (`(Reach x Impact x Confidence) / Effort`) used to prioritize backlog items.
* **Iteration**: In the context of automatic technical debt value increase, an iteration is considered a **finished Tracker item**.
* **Work In Progress (WIP) Limit**: Rules defining the maximum number of items a developer or team can actively work on at any given time.

---

## The Huddle

The **Huddle** is the one recurring meeting for the team, held regularly, for example, twice a week every Tuesday and Wednesday from 10:00 AM to 11:00 AM (or 11:30 AM). Its primary purposes are:

1.  **Reviewing the Backlog**: Collecting new features, user stories, bug fixes, and other valuable items.
2.  **Scoring Items**: Assigning RICE (Reach, Impact, Confidence, Effort) ratings based on team consensus.
3.  **Sorting by Value**: Calculating and sorting items by their Value score (Reach $\times$ Impact $\times$ Confidence) $\div$ Effort.
4.  **Selecting Top Items**: Deciding which items are next for development based on highest Value first, considering WIP limits and dependencies.
5.  **Addressing Blockers & Dependencies**: Reviewing blocked items and actively re-prioritizing or unblocking them (see Handling Dependencies).
6.  **Reviewing Technical Debt**: Briefly assessing the state of technical debt, especially items whose value has automatically increased.
7.  **Cost-Effective Implementation Discussion**: Discussing implementation strategies for items to ensure they meet the "Definition of OK" in the most efficient manner.

**Frequency and Duration**: The Huddle should be held regularly (e.g., twice per work week) at fixed times to maintain rhythm and predictability. Each Huddle should ideally last around 60 minutes, ensuring efficient discussion.

**Understanding Threshold**: Discussions on each item will continue until the entire team achieves at least 80% understanding of its scope, requirements, and implementation approach, aligning with the "Definition of OK" mindset.

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
The **Value Score** is calculated as:
$ \text{Value} = \frac{\text{Reach} \times \text{Impact} \times \text{Confidence}}{\text{Effort}} $
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
