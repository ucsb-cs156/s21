---
num: "Lecture 20"
lecture_date: 2021-05-12
desc: "Wed Lecture: "
ready: false
courses_url: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search
las_url: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las
mapache_url: https://github.com/ucsb-cs156-s21/proj-mapache-search
courses_prod: https://proj-ucsb-courses-search.herokuapp.com
las_prod: https://proj-ucsb-cs-las.herokuapp.com
mapache_prod: https://proj-mapache-search.herokuapp.com
courses_qa: https://proj-ucsb-courses-search-qa.herokuapp.com
las_qa: https://proj-ucsb-cs-las-qa.herokuapp.com
mapache_qa: https://proj-mapache-search-qa.herokuapp.com
team_5pm_1_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/projects/17
team_5pm_2_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/projects/16
team_5pm_3_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/projects/15
team_5pm_4_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/projects/14
team_6pm_1_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las/projects/21
team_6pm_2_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las/projects/20
team_6pm_3_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las/projects/19
team_6pm_4_kanban: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las/projects/18
team_7pm_1_kanban: https://github.com/ucsb-cs156-s21/proj-mapache-search/projects/16
team_7pm_2_kanban: https://github.com/ucsb-cs156-s21/proj-mapache-search/projects/15
team_7pm_3_kanban: https://github.com/ucsb-cs156-s21/proj-mapache-search/projects/14
team_7pm_4_kanban: https://github.com/ucsb-cs156-s21/proj-mapache-search/projects/13
---

# Pull Requests

A few things we didn't say yesterday, but are important to know:

When you are done with your issue, and make a Pull Request:
1. Link the PR to the issue, and/or the issue to the PR.   (Once you make the link, it exists in both directions)
2. Make sure the PR is tagged with your team's tag, e.g. `s21-5pm-1`, `s21-5pm-2`, etc.
3. Make sure to add PR description.  It should briefly describe the change you made *from the user perspective*.
4. Assign yourselves on the PR (the same folks that worked on the issue.)
5. Ask for code reviews from:
   - Members of your team that didn't work on the issue (see [team list here](https://ucsb-cs156.github.io/s21/info/teams/))
   - From the specific LA and TA that are assigned to your team (see [team list here](https://ucsb-cs156.github.io/s21/info/teams/))
   - Don't ask for code reviews from "just everyone" on the staff (though other staff members can do PRs and will sometimes)
6. It can be helpful to deploy the branch on your sites Heroku deployment (the one from the team03 project)

You may see tags such as these:

| Tag | Explanation/What you need to do |
|-|-|
|`FIX ME-MISSING TEAM CR`| Get a fellow member of your team to do a code review |
|`FIX ME-TEST COVERAGE`| Tests may be passing, but they are too many missed lines (i.e. lines not covered by tests).  Improve the test coverage (ask staff for help if you aren't sure how) |
|`FIX ME-CODE REVIEW ISSUES`| Someone requested changes in the Code Review, but you haven't addressed them yet |
|`FIX ME-PR Description`| Your PR doesn't have a description, or the description needs additional attention |
{:.table .table-sm .table-striped .table-bordered}


# How to do a peer Code Review

There are two aspects to doing a peer code review:

* Getting the mechanics right (i.e. clicking on the right buttons in the right way)
* Providing meaningful review and feedback (to help your team improve and keep the quality of the code base high)

Both are important, and arguably the second one is *more* important.  But, let's tackle the first one first.

Doing a code review isn't just making a *comment* such as `LGTM` on the PR.    That's helpful, but it doesn't *trigger* the mechanisms in GitHub's webapp to mark the PR as having been code reviewed.   That requires a specific series of actions on the GitHub web site, done in a particular way.

We'll be putting up a YouTube video explaining that will be published shortly as part of this series:

| Step | Explanation | Video Link | Starting <br /> Kanban Board <br /> Column | Ending <br /> Kanban Board <br /> Column |
|-|-|-|-|-|
| 1 | Have idea, create issue, groom issue | <https://youtu.be/IzMml6aFvRY>  (8:32) | Planning | ToDo |
| 2 | Assign issue to self (and possibly pair partner) | <https://youtu.be/YMDldDQ3e54> (3:46) | ToDo | InProgress | 
| 3 | Work on Issue | <https://youtu.be/DbaBdl1TUuk>  (7:06) | InProgress | InProgress | 
| 4 | Create PR | <https://youtu.be/TKj9AwP10qQ> (TBD) | InProgress | InReview | 
| 5 | Code Review PR / Testing |   Coming Soon | In Review | In Review | 
| 6 | Merging | Coming Soon  | In Review | Done | 
{:.table .table-sm .table-striped .table-bordered}

But in the meantime, I'll give a short live demo turing today's class.

The short version:
* Don't just make a comment
* Use the "Files Changed" tab, and the green `Review Changes` button at upper right.

