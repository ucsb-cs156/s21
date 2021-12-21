---
num: "Lecture 18"
lecture_date: 2021-05-10
desc: "Mon Lecture: "
ready: false
up: 
down: 
sep: 🔸
---

# A short update on Team02

Here's what project planning looks like.... I'll show you:
* A Kanban board
* Planning with cards
* Converting cards to issues
* Adding acceptance criteria


If I just turned you loose on the assignment now, it would be:
* Too big
* Too vague

And it would miss the point of the assignment, which is to be a *gentle* introduction to the frontend.  

I am going through the various React tasks for team02 to ensure that
* The amount of work is reasonable
* There are enough resources so that the work you need to do is reasonably clear
* I've written some new articles:
  - React Introduction (done): <https://ucsb-cs156.github.io/topics/react_introduction/>
  - React Patterns for Components (in progress): <https://ucsb-cs156.github.io/topics/react_patterns/>
  - React Guide to creating a new page (in progress): <https://ucsb-cs156.github.io/topics/react_page_components/>


# First Peer Evaluation survey results 

See your results at CATME.org.  You'll see:
* Your self-rating, and the average of your team's ratings, compared to the average for your team
* You'll see that for a few different scales
* You'll also see comments from your peers

Please look over those, and be prepared to discuss those with your team tomorrow and/or Wednesday.

Note: data is missing for six students that did not fill out the survey.  
* If you are one of those six, please fill it out next time.
* If you notice that the number of comments you got is less than the number of people of your team, please encourage your team
  members to fill it out next time.


# Team03 update

See: <https://ucsb-cs156.github.io/s21/lab/team03/>

All of your apps should now be up and running.
* 10 teams are up and running perfectly
* 1 team is up, but has a problem loading the "Role" from the backend api
* 1 team is still not up at all (home page shows Heroku error message)

For P10, You should each have posted two comments with observations from interacting with your app.

| Section | Team 1 | Team 2 | Team 3 | Team 4 |
|---------|--------|--------|--------|--------|
| 5pm | {{page.up}}[App](https://cs156-s21-team-5pm-1-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-1-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-2-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-2-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-3-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-3-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-4-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-4-courses) | 
| 6pm | {{page.up}}[App](https://cs156-s21-team-6pm-1-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-1-las) | {{page.up}}[App](https://cs156-s21-team-6pm-2-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-2-las) | {{page.up}}[App](https://cs156-s21-team-6pm-3-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-3-las) | {{page.down}}[App](https://cs156-s21-team-6pm-4-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-4-las) | 
| 7pm | {{page.up}}[App](https://cs156-s21-team-7pm-1-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-1-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-2-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-3-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-3-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-4-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-4-mapache) | 
{:.table .table-sm .table-striped .table-bordered}


## P10:P Once your team's app is up, then what?

(Repeated from last Wednesday)

If you haven't done it yet, all members of your team should join slack channel for your teams app (i.e. one of `#proj-ucsb-courses-search`, `#proj-ucsb-cs-las` or `#proj-mapache-search`.)
 
Now, start exploring the features of the app, as individuals and as a team.  

As you explore, make posts to your team's slack channel.  Also monitor the discussions, if any, on the project's channel (i.e. one of `#proj-ucsb-courses-search`, `#proj-ucsb-cs-las` or `#proj-mapache-search`.)

Here are questions that should prompt some posts:
* What do you notice that is broken or confusing?
* What questions do you have about how the app is supposed to work, or what problem it is supposed to solve?
* What changes would you make to the user interface to make it easier to use?
* What new features would you add?
* What other questions/comments do you have based on interacting with the app?


** By Monday, each student is asked to please make at least two posts based on interacting with the app. **

If you haven't done that yet, I'll extend that deadline to midnight Tuesday with a 10% deduction for lateness, but please get it done.


# Today in Breakout rooms

* Go to the NOTES repo for your team
* One person, share screen and create a folder 05.10 at the top level, and inside it, a README.md file.
* In that file, create sections like this:

```
# Notes from 05.10

## Questions

## Bugs 

## UX Improvements

## New Feature Suggestions

```

* Each team member should take turns sharing their screen, bring up the qa version of the app.   Lead the team through a discussion of the things you found and put on the slack.   

* The person taking notes in the 05.05 file should ask the person presenting which category their observation goes in, and then copy/paste it, *along with any team discussion*, into the appropriate section of the document.   After pasting it in, put the team members name in parentheses.

* What gets put into the document should be *more* than just a literal copy/paste of what the person put into the slack.  Include at least something from the team discussion&mdash;at a minimum, was their team consensus on this, or divided opinion?  If team consensus, put, at a minimum: "Team agrees".   What I'm hoping for though, is some richer discussion of the pros and cons of various features.

# To Guide Your Discussion

The overall purpose of the three apps:

proj-ucsb-courses-search
- To be a better version of <https://my.sa.ucsb.edu/public/curriculum/coursesearch.aspx>
- To provide more ways of analyzing that same data
- To provide a way (not yet fully implemented) to build sample schedules

proj-ucsb-cs-las

- To provide a way to keep track of which TAs and LAs are serving which CS courses
- To provide "one stop shopping" for all office hours for all TAs/LAs for all CS courses
  - This is more important when the office hours are in person, and co-located in classrooms
- To provide (not yet implemented) a way to indicate the location of in-person office hours, 
  in a way that admins can tell how many LAs are in a given room at a given time.
- To provide a way to indicate which rooms are available, during which time slots, for TAs/LAs to
  schedule in person office hours.
- To provide a way (not yet implemented) so that admins can limit the number of LAs slots that
  are available in any given room at any given time to avoid overcrowding (this was a problem even 
  before Covid-19, and is likely an even more important issue now.)

proj-mapache-search
- To provide a platform to investigate certain questions about Software Engineering education related to
  - meta-cognition (how do you know when you are stuck, and what do you do when you are stuck)
  - question asking / answering (i.e. good use of Slack to ask and answer questions both of staff and each other)
  - information literacy (how do you find good information on stack overflow)
- To provide access to Slack workspace data even after the 10K limit has been passed
  - Ideally, the UI would be as close to Slack as possible, except that you just can't post new messages (only search and browse)
- Features for analyzing Slack data are intended to 
  * Help students find answers to questions (even after the 10K message has been surpassed)
  * Help instructors find examples of students asking questions
  * Help instructors find examples of staff and students answering questions
  * Potentially, help instructors reward students for asking and/or answering good questions
- Features for Google searches are intended to:
  * Provide a custom search portal that prioritizes websites that pertain to the tech stack used in this course (i.e. good sources
    of data about Spring and React)
  * Provide a way to save and share useful searches and useful links
- It would be nice to provide a way for UCSB CS156 students to mark particular searches as useful to CS156 by
  * upvote/downvote 
  * tagging
  * comments
- The reason for integrating Google Search into the Slack interface is to encouarage searching through the tools, as opposed to using regular Google
  - Ultimately we want to collect data on the searches studnets do, and tie that back to their progress on their projects.
  - To get that data, searching through Mapache Search has to be convenient, and it has to offer added value over just doing a 
    regular Google Search.
  - What features would add that value?
  - What benefit can we get from integration with Slack?
