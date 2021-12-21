---
desc: "Deploying Team Deployment of Legacy Code App (Course Search/LAs/Mapache)"
assigned: 2021-03-04 17:00
due: 2021-03-11 23:59
github_org: ucsb-cs156-s21
layout: lab
num: team03
ready: true
proj-ucsb-courses-search: https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search
proj-ucsb-cs-las: https://github.com/ucsb-cs156-s21/proj-ucsb-cs-las
proj-mapache-search: https://github.com/ucsb-cs156-s21/proj-mapache-search
gauchospace-link: https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=7087487&forceview=1
sep: " &#11045; "
---


This lab is similar to jpa03, in that you will be doing the configuration of a Spring/React full-stack web application that has Google Authentication via OAuth (though Auth0).

Here's what's different:
* Instead of being an individual assignment, you'll complete it as a group.
* Instead of all students in the course deploying the *same* web app, this time you will be deploying the specific legacy code application that you'll be working with later, during the project phase of the course.
  - All 5pm teams will be deploying [proj-ucsb-courses-search]({{page.proj-ucsb-courses-search}})
  - All 6pm teams will be deploying [proj-ucsb-cs-las]({{page.proj-ucsb-cs-las}})
  - All 7pm teams will be deploying [proj-mapache-search]({{page.proj-mapache-search}})
* The setup instructions include all of the steps you did for jpa03, except that:
  - You will need to connect a shared team Auth0 tenant to a Google OAuth client id and client secret.
  - For all three projects, you'll have the additional step of configuring a URL for a MongoDB database
  - For proj-ucsb-courses-search, you'll have an additional step of configuring an API Key for the UCSB Developer API
  - For proj-mapache-search, you'll have the additional step of configuring a Slack Bot
* While you will be _cloning_ a repo for this assignment, you will *not* be creating a new repo.  Nor, do you need to fork a new repo.

  In fact, you don't need a new repo at all.  You'll just be using one of the three existing repos ([proj-ucsb-courses-search]({{page.proj-ucsb-courses-search}}), [proj-ucsb-cs-las]({{page.proj-ucsb-cs-las}}), or [proj-mapache-search]({{page.proj-mapache-search}})) and then _deploying_ it on localhost and then Heroku.
  
  Accordingly, you don't need to worry about configuring Codecov, updating a README file, configuring secrets for CI/CD (`TEST_PROPERTIES`), etc. as you did for
  `jpa03`. Those steps are done by the course staff for these three legacy code repos.

  You have full access to everything except the `main`
  branch of these three repos.   You'll get your code into the `main` branch through "pull requests", which can only be merged by course staff (i.e. GitHub 
  organization
  admins.)

# What we'll have when we are done

When teams are done, the following Heroku applications should be
up and running:

| Section | Team 1 | Team 2 | Team 3 | Team 4 |
|---------|--------|--------|--------|--------|
| 5pm | [App](https://cs156-s21-team-5pm-1-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-1-courses) | [App](https://cs156-s21-team-5pm-2-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-2-courses) | [App](https://cs156-s21-team-5pm-3-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-3-courses) | [App](https://cs156-s21-team-5pm-4-courses.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-5pm-4-courses) | 
| 6pm | [App](https://cs156-s21-team-6pm-1-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-1-las) | [App](https://cs156-s21-team-6pm-2-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-2-las) | [App](https://cs156-s21-team-6pm-3-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-3-las) | [App](https://cs156-s21-team-6pm-4-las.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-6pm-4-las) | 
| 7pm | [App](https://cs156-s21-team-7pm-1-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-1-mapache) | [App](https://cs156-s21-team-7pm-2-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache) | [App](https://cs156-s21-team-7pm-3-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-3-mapache) | [App](https://cs156-s21-team-7pm-4-mapache.herokuapp.com){{page.sep}}[Dashboard](https://dashboard.heroku.com/apps/cs156-s21-team-7pm-4-mapache) | 
{:.table .table-sm .table-striped .table-bordered}

# Why are we doing all of this

In order to be able to work on a full stack web application, you need to be able to:
* deploy that web application on your "own" machine&mdash;whether that's your CSIL account, or your own computer&mdash;so that you can test the effect of your code changes.
* deploy that web application on Heroku to make sure that it works in an environment similar to the one where it will run in production.

These setup steps, as you've already experienced, can be a little complex.  We are introducing them now so that:

* You can get used to them. We don't want these steps to be the stumbling blocks when you are trying to deal with the actual code changes.
* You can start interacting with the app as a user and as an admin, to get to know the functionality of the applications before you start making changes.

# OK, I get that, but what *are* all of these steps?

We can talk more about this in lecture, and I'm happy to... just ask.  But here's a quick run down.

* Auth0 is a "middleware" service for authentication.   It sits between your application and a service such as Google.  Having Auth0 in the middle makes it easier if/when we want to 
  switch authentication methods to, say, Facebook, GitHub, Twitter, LinkedIn, or any number of other companies that could be used for authentication instead of
  Google.
* The `secrets-localhost.properties` file is a file that is read by the Java code when your application starts up; it initializes values in various places in the application code.
  It *should not be checked into GitHub* because the information it contains could be used to compromise the security of your application.
* The `javascript/.env.local` file is read at the time your application starts up, and is used to initialize values in the front-end JavaScript code.  Like
  the `secrets-localhost.properties`, it should not be checked into GitHub (for the same reason).  This file is also used by the `setHerokuVar.py` script to
  initialize a few "Config Vars" on the Settings page of your Heroku app, values that are read into the front end JavaScript code when the application first
  starts up.
* The `secrets-heroku.properties` file is used by the `setHerokuVar.py` script to
  initialize the "config vars" called `SPRING_PROPERTIES` on the Settings page of your Heroku app.   
  These values are read by the Java code on Heroku when your application first starts up.


If you have more questions, ask in lecture, in office hours, or ask the TAs/LAs during section.
  
# Steps 

Steps 1 and 2 can be delegated to individual members of your team, and done in parallel with the remainder of the steps.


## Step 1: Give everyone on your team access to your Heroku app 

On your team's slack channel, you should find a message about your {{page.num}} Heroku app.  The name of the app will be something like this:

Examples:
* <https://dashboard.heroku.com/apps/cs156-s21-team-5pm-3-courses>
* <https://dashboard.heroku.com/apps/cs156-s21-team-6pm-4-las>
* <https://dashboard.heroku.com/apps/cs156-s21-team-7pm-2-mapache>

Some on your team was given admin access to the app.  Identify that person.  They should add everyone else on your team, using the 
email address that person uses to login to Heroku.

If that person is not available, there is an LA designated for your team.  Ask them, or one of the TAs, or the instructor, to add someone else from your team, and then *they* can add everyone else.

## Step 2: Give everyone on the staff access to your Heroku app

On the Slack, in the channel `#course-notes`, there is a list of the email addresses of the course staff.    Some of them already have access to your app, but the rest do not.  Please add the rest of them.

## Step 3: Clone the Repo assigned to your team.

This step should be done, eventually, by each member of the team individually.  For today, though, it is sufficient for one member of the team to do it,
preferably, sharing their screen with other members looking on and helping.

Identify the repo associated with your team:

 - All 5pm teams: <{{page.proj-ucsb-courses-search}}>
 - All 6pm teams: <{{page.proj-ucsb-cs-las}}>
 - All 7pm teams: <{{page.proj-mapache-search}}>

Clone this repo on your local machine, or in your CSIL account.

## Step 4: Follow the SETUP-QUICKSTART.md instructions to create a `temp-credentials.txt`

Next, follow the SETUP-QUICKSTART.md instructions for your repo. 

Note that you should be able to use these instead of the `SETUP-FULL.md` instructions,
since you should already have:

* a shared Auth0 tenant for your team
* the `Connections`/`Social`/`Google` clientId and clientSecrets populated with values

So, following these instructions:

* First, create a `temp-credentials.txt` file.  Note that this file does *not* get committed to the GitHub repo!
* For the app name, use the name of the already existing Heroku deployment that was shared with you on your team's slack channel.
 
  For example:
  * 5pm teams: `cs156-s21-team-5pm-1-courses`,  `cs156-s21-team-5pm-2-courses`,  `cs156-s21-team-5pm-3-courses` or  `cs156-s21-team-5pm-4-courses`
  * 6pm teams: `cs156-s21-team-6pm-1-las`, `cs156-s21-team-6pm-2-las`, `cs156-s21-team-6pm-3-las`, `cs156-s21-team-6pm-4-las`
  * 7pm teams: `cs156-s21-team-7pm-1-mapache`, `cs156-s21-team-7pm-2-mapache`, `cs156-s21-team-7pm-3-mapache`, `cs156-s21-team-7pm-4-mapache`
  
  
## Step 5: Setting up shared Auth0 tenant

Two members of your group shoudl have an invitation to a shared auth0 tenant with a name such as:
* `cs156-w21-team-5pm-1`


Find out which of these group members are present; one of them should be assigned to jobs "A" and "B".

* A: Inviting all team members to a shared Auth0 tenant (see note below)
* B: Inviting all staff to your shared Auth0 tenant (see note below)


If no-one has such emails, ask for help on the `#help-lecture-discussion` channel on Slack; one of the staff will invite one of the members of your group.

First task is to accept your own invitation.

Next, switch tenants to the team tenant (there is a "Switch Tenant" option in the menu at the upper right of the Auth0.com dashboard, where your login name is.)

Then, from the same menu, choose the "Invite Admin" feature to invite the other admins.

The person with job "A" should get the `@ucsb.edu` email addresses of all of the other team members.

The person with job "B" should get the `@ucsb.edu` email addresses of all of the staff; these are posted in the `#class-notes` channel on the course Slack.

When you have finished inviting all of the other members of your team (A) or the staff (B), you are done with
this task. 

## Step 6: Create an application, API and custom rule as in jpa03

* Switch to your shared Auth0 team tenant (e.g. `cs156-s21-team-5pm-1`, `cs156-s21-team-5pm-2`, etc.) when you are creating the app in Auth0
* Follow the usual instructions to create an application, create an API, and a custom rule. 

Also: add the additional steps needed, depending on your particular application:
* For `proj-ucsb-courses-search`, you should have a value for the `app.ucsb.api.consumer_key` that was posted to your team's slack channel.  Fill that in.
  This is a value obtained from <https://developer.ucsb.edu/> on your behalf.
  - You may also apply for your own account and obtain your own value if you wish, but there is sometimes a delay in getting new accounts approved.  This value
    is obtained on your behalf by the instructor.
* For all three apps, there will be a value for a URI to connect to a MongoDB database.   This value will be supplied to you on your team's slack channel, or
  perhaps through DMs to one or more of your team members. 
* For mapache-search, there will also be values you need to configure for a custom Slack bot.   These will also be conveyed to you via Slack.


Once you've filled in all these values in your `temp-credentials.txt`, distribute these among the members of your team. 

It is best to do this via Slack DMs rather than in a public message on the team slack channel. 

## Step 7: Configure your `secrets-localhost.properties` and `javascript/.env.local` files

Next, set up the values in  `secrets-localhost.properties` and `javascript/.env.local` files, and  `secrets-heroku.properties`  using the values
from `temp-credentials.txt`.

For the `app.admin.emails` value, add half of the team members to the list, and *leave half off*:

```
app.admin.emails=phtcon@ucsb.edu,cgaucho@ucsb.edu,foobear@ucsb.edu,ldelplaya@ucsb.edu
```

Here's why: as a team, you want to be able to test with, and without admin privileges.   The users you list here are "permanent admins" that *always* have admin privileges.  The rest can be shapeshifters; existing admins can turn admin privileges on/off for these users.

You should always have at least one permanent admin on your team, but it is good to have several folks that can test the application in both admin and non-admin mode.

You might distribute these files via DMs on slack also.

## Step 8: Test the application on `localhost`

Now, with the values in place in `secrets-localhost.properties` and `javascript/.env.local`, you should be able to run your application using

```
mvn spring-boot:run
```

Make sure it comes up on localhost, and that you can login and logout.

## Step 9: Run `setHerokuVars.py` and then deploy on Heroku

Next, run the `setHerokuVar.py` script (following the instructions), and then deploy your main branch on Heroku.

You should be able to access the application, and then login, and logout.


## Step 10: Test the admin features

Check that the permanent admins have access to the admin menu.

Then, try having some non-admin members login to the app.  After they login, admins should be able to see their logins on the admin menu.

They should also be able to `promote` and `demote` these users, giving and taking away admin status.

When all of this is done, you're basically finished with this lab, and ready to submit it on Gauchospace.

## Step 11: Submit on Gauchospace

One member of your team should submit here: 
<{{page.gauchospace-link}}>


