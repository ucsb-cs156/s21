---
num: "Lecture 23"
lecture_date: 2021-05-19
desc: "Wed Lecture: "
ready: false
---


# Tradeoffs: Quick Win, vs Maintainability

A case study: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/pull/292

Tradeoff:
* Can get the italics quickly by just modifying a few lines of code
  - Upside: quick, easy to understand
  - Downside: But the code might become hard to read, understand, maintain
* Alternative: put a css class on the elements that marks them as "sections"
  - Set the style for all sections in one place.
  - Downside: will take longer to do

Bottom line: for the short term
* Sometimes the quick win is the better way to go
  - Team morale
  - Getting something in front of the customers for feedback
  - Competiton (in a real world settting), and avoiding churn
* Sometime the more maintainable solution is the better way to go
  - If there isn't a pressing need
  

It's a good idea though, when you do the "quick win" to have a concrete plan for refacoring.
* Quick wins can accumulate into tech debt

As Bryan points out:

> I think something we might want to make more clear to the students is that they will be expected to refactor/rewrite existing code in some cases, and that the code already present in the codebase isn't necessarily the best example of good design


This is absolutely true, and it's also going to be true of real world software development settings.


# The default plan today, with one addition


Plan for lecture today: same as section yesterday, after a short discussion in the main room.  Plus one twist : each team make a post on the project channel describing PRs done, and those in progress/planned.

# The default plan

(1) Virtual standup: Each team member present posts in the slack channel for the chat an update with

(a) what stories they've worked since last time
(b) status of each of those
(c) any blockers
(d) what they will work on next.

If you don't know to work on next, say that for (d).

(2) Actual out-loud standup.   Go over what you posted in the slack channel.

(3) Review kanban board, right to left.  Try to get stuff merged and code reviewed (as a team) before taking on new stories.

But if you have done everything you can and are just waiting on staff, then start work on a new story.
If you don't have enough stories to work on, alert the staff.

TODAY ONLY: Please a post on your project channel #proj-ucsb-courses-search, #proj-ucsb-cs-las, #proj-mapache-search

(1) team number
(2) theme
(3) Summary the PRs that your team has merged into main
(4) Summary of the work that your team is working on now.

WHY?  This is not just "copy/paste" from your issues or PR descriptions, nor is it just busy work.

Purpose: inform other teams of info they may need to know in order to do *their* work.

Think about what level of detail would other teams really need...   not too much detail, but just enough so that other teams have a notion of whether or not their work and your work are complementary, on a collision course, etc.

(4) Work on your stories, either together, or in separate breakout rooms.


# Note

Note  that ^^^^ THIS ^^^^ is the default plan for every class from now to the end of the quarter, unless we instruct you otherwise.    We may occasionally deviate from this, and there may be announcements, but this is the typical way that class goes.    (This is also the typical way that devs work in real world sw dev teams.... except that instead of alerting the "staff" for new stories, it would be a shared team responsibility to work with the "product manager" and "ux designers" to come up with the new stories.)


