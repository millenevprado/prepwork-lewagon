# TECHNICAL WORKFLOW FOR A STARTUP :briefcase:

Workshop video: [Technical Workflow for a Startup](https://www.youtube.com/watch?v=iZkP9rcEJEM&t=12s)

<h2> <a name = "startup"></a>STARTUP</h2>

A startup is a temporary organization formed to search for a repeatable and scalable business model (STEVE BLANK, 2010). Once you find a business model, you're no longer a startup.

<h2> <a name = "versioning"></a>VERSIONING</h2>

Backup versions of your work and track modifications (here, we add check-points to the code/work). With GitHub we can have a Timeline to track the work. 

### How to Read a Repository

- See the contributors (who is working on the code)
- Take a look at the commits (the check-points of the code)
- See the code

<h2> <a name = "workflow"></a>WORKFLOW</h2>

The workflow that GitHub has defined is based on using Branching and Pull Requests. To add a feature that you want to implement inside the project, we can Branching and Pull Requests. So, how does it work? 

- CREATE A BRANCH: we create it to make the changes that we want. We don't make the changes directly on the master, we work on the **branch** first.

  ![](images/workflow-create-a-branch.png)

- WORK AND COMMIT:

  ![](images/workflow-work-and-commit.png)

- OPEN A PULL REQUEST: submit your work on GitHub through **pull requests**. Write a clear and objective message, if possible, with screenshots of the changes that have been made.

  ![](images/workflow-pull-request.png)

- REVIEW: After making all the changes I wanted, I now want someone to take a look at my work, to review the code. Revisions are important because we want the code to look like it was written by a single person.

  ![](images/workflow-review.png)

- MERGE: after the revision and all changes have been made, it is possible to merge the work into the master (to the main line).

  ![](images/workflow-merge.png)

<h2> <a name = "deployment"></a>DEPLOYMENT</h2>

After the changes have been made, and we've made sure they are working on the computer, we can deploy the work. 

At Le Wagon they use [Heroku](https://www.heroku.com/), which hosts the code in the cloud so that the content is visible to customers accessing the site (it's a server). 

![](images/deployment-heroku.png)

In the GitHub workflow, we have a rule, which must be respected: "**ANYTHING IN THE MASTER BRANCH IS DEPLOYABLE**." When we merge the code into the master, we have to make sure the code is running correctly.

### Continuous Deployment

- Deploy your app in production with quick command lines.
- Continuous delivery ensures minimal impact from bugs, and fast feedback from users.

### Automated Deployment

A tool to automatically deploy at every change of the master branch. 

![](images/deployment-automatic-deploys.png)

![](images/deployment-merge-button.png)

With this kind of process, we can ship really often. But this can cause some problems. For example, if you have 10 deploys per day, some might break, which is not good for startups (we can't break stuff in this case).

![](images/deployment-break.png)

And if we break something, we can just **ROLLBACK**, reverting the code to where it was before it broke.

<h2> <a name = "testing"></a>TESTING</h2>

How can we prevent breaking things? We can prevent TESTING!

When we have a site with many features, we can write a code to automate the test and check when a change is made (a new feature is added), if this change hasn't affected any of the other features. **The best practice is to write a test code to every feature**.

- Never push your code without testing! ⚠️
- Implement Test-Driven Development to avoid huge future technical debt.
- Implement bug tracking and reporting.

### Travis CI

Travis CI automatically test every commit pushed on every branch. We get a feedback inside the pull request if we broke something (visual feedback: green and red button).

<h2> <a name = "continuous-deployment"></a>CONTINUOUS DEPLOYMENT</h2>

- Deploy your app in production with quick command lines.
- Continuous delivery ensures minimal impact from bugs, and fast feedback from users.

"The key test is that a business sponsor could request that the current development version of the software can be deployed into production at a moment's notice - and nobody would bat an eyelid, let alone panic."

### Advantages

- Reduced deployment risk - because you don't deploy a lot of stuff at once.
- Real sense of progress (done - the code is in the hand of the end user, the customer)
- User feedback

<h2> <a name = "backups"></a>BACKUPS</h2>

When we make a change to the code and break something, for example, we can rollback and go back to the code that was working. However, when we have a database and, for example, we delete a column, when we rollback that column does not come back, so it is necessary to have a **backup for the database**. That way we can restore the data.

Prevent the loss of data with automatic backups of your database.

<h2> <a name = "monitoring"></a>MONITORING</h2>

It consists of checking if the website is working correctly, and if it is always working.

![](images/monitoring.png)

This software updates your page every 5 seconds and if the site is down it sends you an email. But sometimes more information is needed, so there are software that detect errors, such as raygun.

![](images/monitoring-raygun.png)

<h2> <a name = "issue-tracker"></a>ISSUE TRACKER</h2>

Every time you see a bug you need a place to tell someone there is a bug. 

Embrace simplicity!

<h2> <a name = "advices-from-a-developer"></a>ADVICES FROM A DEVELOPER</h2>

- Resist meta-work (when we stop to talk about work and how we're going to do the work)
- Avoid meetings
- Write everything (like in slack)
- Embrace asynchronicity
- Don't pull me from the zone