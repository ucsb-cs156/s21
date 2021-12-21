---
num: "Lecture 24"
lecture_date: 2021-05-24
desc: "Mon Lecture: "
ready: false
sep: 🔸
---

# In Breakout rooms

Here's a reminder of usual procedure when we put you in breakout rooms (with extra items for today highlighted)  

(1) Virtual standup: Each team member present posts in the slack channel for the chat an update with
* (a) what stories they've worked since last time
* (b) status of each of those
* (c) any blockers
* (d) what they will work on next.
 
If you don't know to work on next, say that for (d).

(2) Actual out-loud standup.   Go over what you posted in the slack channel.

(3) Special steps for today:
* (a) Make sure someone on your team has agreed to have the team's QA repo transferred to them
  - That person should post the email they use for Heroku in the team's slack channel with an `@` mention to Conrad
  - When Conrad responds, transfer the repo, and redeploy a branch and make sure it is working
* (b) Designated who will present for team tomorrow night during section. Post their name on the slack channel.
* (c) Post a team strategy to get to 100 points.
  - Suggest: a list of the issues the team is working on, and how many points they they think they are worth.
  - You might also ask staff to do a sanity check on that... e.g. tag your TA and LA and ask them to do an estimate on each story.

(4) Review kanban board, right to left.  
* Try to get stuff merged and code reviewed (as a team) before taking on new stories.
* But if you have done everything you can and are just waiting on staff, then start work on a new story.
* If you don't have enough stories to work on, alert the staff.


(5) Work on your stories, either together, or in separate breakout rooms.


# Agenda for today
1. Information about final exam slot: 
   * It won't be a written exam, but it is required
   * Each team will make a video presentation 
   * You'll be ranking the presentations into four tiers (upper 25%, next 25%, next 25%, bottom 25%).
   * The course staff will also be doing these rankings.
   * Student rankings will not be used *directly* to impact grade
     - Those will be taken primarily from the staff rankings
     - BUT, student rankings will be used as a "sanity check" or a "tie breaker" in the case that staff rankings are ambiguous.
     - So please do take these seriously.
   * More info on the presentations soon
2. Deadlines: Please finish up all of your legacy code stories to get to 100 points by 5pm Friday afternoon, 05/28/2021
   - You do not necessarily have to have everything merged by then, but you *should* have made the PRs.
   - After 5pm Friday, you might still be working on getting CRs done, addressing CR feedback
   - But the coding to implement the feature, and get test cases to pass should be done
3. Today: In addition to standup, make a team strategy to get to 100 points.
   - Assess where you are.  Are you at 15/100, 50/100, or 75/100?  Strategy will be different in each case.
   - Look at your backlog (stories in Planning and Todo columns).  Do you have enough?
   - Do you need stories there pre-estimated in terms of point values?
4. Updating owners on Heroku app (details below)
5. Designate a team member to present in Tuesday section during first 15 minutes (2-3 minutes per team)
   - This can be an "oral report" version of what you put on the project slack channels last week.
   - Demo the features that your team has merged into the `main` branch, showing them in the production app
     - If it's something that can be *seen* in the app, show it there.
     - If they are pure refactoring, then show the before and after in the code, and explain why the new code is better.
   - Briefly describe the feature(s) that your team is working on.
   - The *purpose* of this is so that you can be aware of what other teams are working on, and identify any areas of overlap or potential conflict.
6. We are working on standardizing the team labels, moving from e.g. `s21-4pm-3` to `s21-4pm-3-AdminFeatures`  

# Need to update owners on Heroku app

Each team has a Heroku app, such as these examples:

* <https://dashboard.heroku.com/apps/cs156-s21-team-5pm-4-courses>
* <https://dashboard.heroku.com/apps/cs156-s21-team-6pm-1-las>
* <https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache>

I created all of these myself and then linked the three legacy code apps to them
* Heroku requires you to have admin permission to the repo in order to link a Heroku app to a repo
* That's why I created them myself

But, that means all 12 of these have been drawing from my personal quota of "free tier" time, and my time is up for this month.

So, if we want these apps to continue to run, we need to transfer them to a member of your team.
* Please go on your team's dashboard, and look at the emails there
* Let me know which team member is willing to accept a transfer
* Put that email on your team's slack channel, and mention me (Phill Conrad) in the post.
* I'll go through during today's team breakout session and transfer each of these.


| Section | Team 1 | Team 2 | Team 3 | Team 4 |
|---------|--------|--------|--------|--------|
| 5pm | {{page.up}}[App](https://cs156-s21-team-5pm-1-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-1-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-2-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-2-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-3-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-3-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-4-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-4-courses) | 
| 6pm | {{page.up}}[App](https://cs156-s21-team-6pm-1-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-1-las) | {{page.up}}[App](https://cs156-s21-team-6pm-2-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-2-las) | {{page.up}}[App](https://cs156-s21-team-6pm-3-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-3-las) | {{page.down}}[App](https://cs156-s21-team-6pm-4-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-4-las) | 
| 7pm | {{page.up}}[App](https://cs156-s21-team-7pm-1-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-1-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-2-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-3-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-3-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-4-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-4-mapache) | 
{:.table .table-sm .table-striped .table-bordered}

