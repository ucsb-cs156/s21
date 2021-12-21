---
num: "Lecture 17"
lecture_date: 2021-05-05
desc: "Wed Lecture: continue team03"
ready: false
up: ✅ 
down: ❌
sep: 🔸
---

# First Peer Evaluation survey (participation grade P10), due Friday

* Sometime between now and Friday, please look into your email for an invitation to fill out the CATME.org activity ("PeerEval1").
* This one will take longer than the subsequent ones, because there are more questions.  Later ones will have fewer questions.
* Should take < 30 minutes

Your peer ratings may be:
* higher than the average for your team, 
* the same as the average for your team, or 
* lower than the average for your team.

In cases where the spread is small, these peer ratings will not signficantly impact your grade. But, in cases where the performance is
significantly higher or lower than the mean (measured by standard deviation), we may apply a multiplier to your grade that increases
or decreases it.    

Purpose:
* To learn from our peers about our how they perceive our teamwork skills
* To promote fair distribution of work withing the team (avoiding "free loaders").
 
Separately from how your teammates rate you: 
* The act of filling out the survey itself, always impacts your grade (as a participation activity).  
* So please do it, and do it promptly.

I'd like this done by Friday so I can analyze result over the weekend, and share them before Monday's class meeting.


# Team02 update

* We'll start on this next week, in parallel with our first round of "simple stories" on the legacy code apps.    
* Ideally, it would have been sequential, but I think this will still work.

# Team03 update

See: <https://ucsb-cs156.github.io/s21/lab/team03/>

Here's the status as of 10am this morning:

When teams are done, the following Heroku applications should be
up and running:

| Section | Team 1 | Team 2 | Team 3 | Team 4 |
|---------|--------|--------|--------|--------|
| 5pm | {{page.up}}[App](https://cs156-s21-team-5pm-1-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-1-courses) | {{page.up}}[App](https://cs156-s21-team-5pm-2-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-2-courses) | {{page.down}}[App](https://cs156-s21-team-5pm-3-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-3-courses) | {{page.down}}[App](https://cs156-s21-team-5pm-4-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-4-courses) | 
| 6pm | {{page.down}}[App](https://cs156-s21-team-6pm-1-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-1-las) | {{page.down}}[App](https://cs156-s21-team-6pm-2-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-2-las) | {{page.up}}[App](https://cs156-s21-team-6pm-3-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-3-las) | {{page.down}}[App](https://cs156-s21-team-6pm-4-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-4-las) | 
| 7pm | {{page.down}}[App](https://cs156-s21-team-7pm-1-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-1-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-2-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-3-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-3-mapache) | {{page.down}}[App](https://cs156-s21-team-7pm-4-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-4-mapache) | 
{:.table .table-sm .table-striped .table-bordered}

I'd like to see all of those as {{page.up}} by the end of class today, so that you can start your next team activity: getting to know your legacy code app as an end user, and as an admin.

To be clear: the {{page.down}} marks are all on pages that *have not yet even attempted* to deploy the app on Heroku.  So let's briefly go over is required to get the app up on Heroku:

* You need to have set the *Config Vars* for your Heroku deployment, including `SPRING_PROPERTIES` and a few others.  How you do it:
  - putting appropriate values into `secrets-heroku.properties` (that can be a detailed process)
  - running the script `./setHerokuVars.py your-app-name-here`

  Here's how you see if you can check whether your config vars are set at all (this doesn't verify that you have correct values, but if values for these
  *don't* show up, it's 
  definitely *not* going to work:
  
  ![Checking whether config vars are set on Heroku](are_config_vars_set.gif)

* You have to actually hit the deploy button: it looks like this

  ![Deploying on Heroku](deploy-heroku-app.gif)

    
# What is a *qa deployment* of an app?

We speak of a *deployment* or *instance* of an app as a separate instance of the app running somewhere.

These app instances, one per team, are intended to be *quality assurance (qa)* deployments. 

They are to be used for testing out changes to the app so that you can be "assured" 
that they improve the "quality", before doing a pull request to merge them into the `main` branch.

# Are these instances fully separate, or do they share any data in common?

Usually, these separate instances work from separate databases; this is necessary and appropriate when
the app has read/write access to the databases.

In a few cases, they apps all share a common database; this is typically possible when the database is read only,
and the database schema (the way in which the information is structured), is not changing much, or at all:
  
Here are the details:
- For all three apps, all SQL tables are individual to each app deployment; none are shared across deployments. The only shared databases are MongoDB databases.
- For `proj-ucsb-courses-search`, all deployments use the same read-only MongoDB database that stores old course
  information.  Our schema matches that used by the ucsb developer api for course info, so it doesn't 
  change except where their API changes, which is rarely, if at all.  The course staff run scripts to update
  the data in this database. 
- For `proj-ucsb-cs-las`, the MongoDB database is read/write (for storing user logins) and is specific to 
  each deployment of the app.
- For `proj-mapache-search`, deployments for a particular quarter share a common database with information
  about the Slack workspace for that instance of CMPSC 156.    The schema matches the Slack workspace
  data export format, which changes rarely, if at all.   The course staff run scripts to update
  the data in this database.

# Getting to know your team's legacy code app

The team's qa apps can also be used to get to know the app's features, *especially the admin only features*.

You can get to know the legacy code apps as user to *some extent*, by using the three production versions:
* <https://proj-ucsb-courses-search.herokuapp.com>
* <https://proj-ucsb-cs-las.herokuapp.com>
* <https://proj-mapache-search.herokuapp.com>

However, each of the apps has "admin only" features that you need to be an administrator to access.  We generally don't give admin access on the production apps to students in the class, so to test admin features, you need to have your own instance of the app.

# Deploying Apps on Heroku: Linking requires Admin access to the repo

To deploy an  app on Heroku, the Heroku app needs to be linked to the repo by someone that has "admin" access to the repo.   This is why we created these Heroku apps on behalf of each team.   

Sometimes, teams may need an additional Heroku instance of their app.  
Here are some workarounds:

* Create a Heroku app, add one of the staff as a collaborator, and have the *staff member* do the initial
  linking of the repo to the Heroku app (the staff member can, because they have admin rights to the repo).
  After that, you can deploy the app as often as you like.   This would allow the team to have as many
  qa instances of the app on Heroku as you have slots for on your Heroku plan.
  
* Fork your own copy of the legacy code app, one in which you have full admin rights.  "Forking", in this case,
  refers to a specific GitHub feature where you can have a separate app on GitHub, with a separate owner,
  but that it linked back to the main repo.   You can do pull requests between forks of the same repo.
  
  Since you can do pull requests across forks, this would probably still be compatible with the workflows
  for the course.  However, managing forked copies of repos introduces an 
  extra layer of complexity, and offers no known advantages other than the ability to deploy on Heroku, so
  we've avoided it thus far.  
  (Some extra complications include setting up repo level Secrets for the CI/CD workflows, integration with Codecov, etc.)

# In your breakout rooms:

## Today's first goal: Up and running

The first goal is to get your team's app is up and running, i.e. so that when you click the "App" button, you see
a home page similar to the ones shown below, and can use the `login` button to login:

| [proj-ucsb-courses-search](https://proj-ucsb-courses-search.herokuapp.com) | [proj-ucsb-cs-las](https://proj-ucsb-cs-las.herokuapp.com) | [proj-mapache-search](https://proj-mapache-search.herokuapp.com) |
|-|-|-|
| ![proj-ucsb-courses-search-home-page](proj-ucsb-courses-search-home-page.png) | ![proj-ucsb-cs-las-home-page](proj-ucsb-cs-las-home-page.png) | | ![proj-mapache-search-home-page](proj-mapache-search-home-page.png) |

Then, you should edit the variable that sets the initial admins, to include some from your team.  That looks like this:

* In `secrets-localhost.properties` and/or `secrets-heroku.properties`, change this line, or add a line:
  
  - Change: `app.admin.emails=phtcon@ucsb.edu`
  - To: `app.admin.emails=phtcon@ucsb.edu,cgaucho@ucsb.edu,ldelplaya@ucsb.edu`, where `cgaucho@ucsb.edu` and `ldelplaya@ucsb.edu` are two 
    members of your team.  You might also add the emails of [your assigned LA and TA](https://ucsb-cs156.github.io/s21/info/teams/).
    
* When running on localhost, changes take place when you restart the backend.
* When running on Heroku, for the changes to take place, you need to rerun the `setHerokuVars.py` script.

Those team members should then be able to see the admin menu.  These admins are called "permanent admins", because their admin status
is hard coded into the environment variables.   On the admin menu, they should be able to promote other users that have
logged in to admins.  For these users, their admin status is stored in the database.

## Once your team's app is up, then what?

If you haven't done it yet, all members of your team should join slack channel for your teams app (i.e. one of `#proj-ucsb-courses-search`, `#proj-ucsb-cs-las` or `#proj-mapache-search`.)
 
Now, start exploring the features of the app, as individuals and as a team.  

As you explore, make posts to your team's slack channel.  Also monitor the discussions, if any, on the project's channel (i.e. one of `#proj-ucsb-courses-search`, `#proj-ucsb-cs-las` or `#proj-mapache-search`.)

Here are questions that should prompt some posts:
* What do you notice that is broken or confusing?
* What questions do you have about how the app is supposed to work, or what problem it is supposed to solve?
* What changes would you make to the user interface to make it easier to use?
* What new features would you add?
* What other questions/comments do you have based on interacting with the app?


By Monday, each student is asked to please make at least two posts based on interacting with the app.
