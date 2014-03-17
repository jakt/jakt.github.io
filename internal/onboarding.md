# Welcome to JAKT

Welcome! Here is a document covering a variety of computer setup and programming
related questions that will help our team work best together.

This is a living document, changes, additions are expected and encouraged. If
you find a section is lacking make some changes and submit a pull request.

## Before Your First Day

These things need to be completed before you come in on Day 1.

### Accounts Setup

You will need an `@byjakt.com` Google Apps account. This encorporates your email
and calendaring. Bug [Josh][josh@] if you have not received an
invite to Google Apps.

#### Dropbox

You will also need to be added to our Company Dropbox account. We have Dropbox
for Business that allows you to keep both your personal *and* our company
Dropbox accounts without merging them.

Once you have Dropbox setup it would be a good time to browse around and see
how the folders are structured. Yes, in a perfect world perhaps we could
[remove the concept of nested folders][ia: new file system] but for now there
is a very general layout of how things are structured.


    ├── Clients           Client projects folder
    ├── Forms             Legal and other forms
    ├── Personnel         Personal folders for each employee
    │   └── YOUR NAME     Your personal folder
    ├── Assets            Various purchased assets including images and fonts.
    └── Books             Various purchased books, good for reading


#### FogBugz & Kiln

We'll be giving you access to our bug tracking and scm solution. These are
handled by FogBugz and Kiln. See the section's below entitled
[Working with FogBugz](#workingwithfogbugz) and
[Development Workflow with Kiln](#developmentworkflowwithkiln) below.

## Communication

Clear and constant communication is a priority for our team. We have a short
(<3 minutes) daily standup at 10:15am every morning. You have ~20 seconds to
explain what you've completed, what you're working on, and what (if any) issues
are blocking you. Here are three main communication tools we use at JAKT.

#### Email

You will be given an `@byjakt.com`. You should be in the habit of checking your
email a few times a day. Email is not a reliable real-time messaging platform
but often people expect replies quickly. If something more urgent comes up, you
are expected to be available on the common real-time messaging platforms below:

#### Slack

Slack is a team communication service that integrates with many different
services. The core of Slack is built around an IRC-style layout with various
channels that are used. Direct messaging is enabled as well. There are web,
desktop, and mobile clients available.

#### Messages

Messages is an Apple-only messaging client that supports the following account
types out of the box:

 * iMessages (for iOS and iCloud users)
 * Google Talk
 * Other jabber accounts
 * AIM
 * etc.

#### Other Solutions

We're actively investigating new solutions that will help us communicate better.
If you stumble across one that looks good let us know!

## Working with FogBugz

There isn't very formalized process for using FogBguz. I'm detailing some basic
guidelines for how we use it but one of the best resources for you to go over is
the FogBugz help desk, especially the
[FogBugz in Two Minutes][fogbugz two minutes] video.

#### Projects

We create one project per client. All cases for a project go within here.

#### Areas

Areas within a project are used to separate logical types of work. For starters
each project will have an area called “Misc.” As the project grows we will
expand the number of areas slowly to accommodate certain filters or grouping of
cases.

#### Category

The type of case. They are relatively self-explanatory.

* **Bug** is for bugs.
* **Feature** is for improvements or additions.
* **Task** is for things that are not features or bugs (use sparingly).
* **Inquiry** is for research or customer requests.
* **Schedule Item** is for meetings or other misc. time spent on that project.

#### Case Status

Each category has different statuses you can assign it. The three major statuses
are:

* **Active** Case is active.
* **Resolved** Case is considered complete by the person who resolved it.
* **Closed** Case is closed out, deployed, and confirmed. Typically you will not
be closing cases, only resolving and assigning them to your team lead for
deployment and closure.

If you open a case for someone else to complete it is there responsibility to
resolve it and assign it back to you. At that point it's your responsibility to
verify that the case is complete and close it out.

#### Kanban

The kanban board is used to track the status of cases as they move through the
system. Currently there are six columns:

 * **Proposed** The case is proposed. This is the initial state for any new case
 unless immediate action is being taken upon it.
 * **Approved** When a case is assigned to you it is your responsibility to give
 that case an estimate and due date. Once this is done move the case to
 approved.
 * **In Progress** When starting work on a case first double check to make sure
 the estimated time is accurate. Then move the case to *In Progress* and start
 time for the case.
* **Ready for Testing** When a case is complete resolve it and at the same time
move the case to the *Ready for Testing* column. This indicates that you believe
the case to be complete. When resolving the case it will default to the person
who opened it. Ensure this is the correct person to be checking your work.
* **Ready to Ship** For cases that require a deployment step, once they are
tested move it to this column until the next release occurs.
* **Shipped** Cases that are deployed or finalized are added here. When a case
is moved to *Shipped* it should be closed.

#### Kanban Colors

We were experimenting with kanban colors previously using a color per-project.
Now we're using colors to better indicate case status. Important colors are:

 * **Blocked**: Means there will be no forward progress on a case until
 something happens, either waiting for a reply, a bug is fixed, or something
 else. *Blocked* cards should be given the highest priority because it means no
 work will be done until the blocking issue is resolved.
 * **Normal**: Means the case is progressing correctly within the set estimate
 and due date. This should be the status for the majority of cases on the kanban
 board.
 * **Bug**: Is a special “Normal” status set aside for cases that are set in the
 [*Bug* category](#category). Bugs should be fixed as soon as possible so they
 are given a differentiating color.
 * **Indeterminate (default)**: The fourth color is for cases that have not been
 reviewed by the person they are assigned to. Please review cases that are
 assigned to you sooner rather than later so that the estimates and due dates
 are accurate.

#### Assigned To

Who is currently responsible for handling the case. Cases can be passed through
team leads and onto individual developers or they may be directly assigned. If a
case is assigned to you and you believe it is better handled by someone else or
more information is required make a note when editing and assign it to the new
person. Keep in mind you should be moving it back to the *Proposed* kanban
column when doing so.

#### Priority

Current priority of the case. When in doubt, work on highest (1 high, 7 low)
priority cases before lower priority cases.

#### Milestones

Milestones are used to track progress towards an finalized release. Typically
this is a version number but other milestones are possible. There is a global
milestone available to all projects called *Undecided*. There should also be a
milestone called *General* that is available per-project. If the case does not
apply to a current milestone in the project please attach it to the *General*
milestone. If the case does not really apply to the project but you’re not sure
where to put it, put it on the *Undecided* global milestone.

#### Other Fields

* **Parent Case** Parent case (makes this case a subcase)
* **Subcase** Subcases (makes this case a parent case)
* **Due** Date and time this case is estimated to be done by.
* **Estimate** Estimated time it will take to resolve this case. FogBugz enables
[evidence based scheduling][fogbugz: ebs] so all cases must have an estimate.

## Development Workflow with Kiln

We're using Kiln because it's enables our development teams to use git or
mercurial as they like. It gives us the ability to branch repositories cleanly,
perform code reviews with sign-offs, and it ties into our case management system
in FogBugz.

#### Starting a Project

All developers will have their own branch repositories off of the main
repository. This repository is your playground; you are free to merge and rebase
commit history to your heart's content.

That said, the main repository is a church. Everything in it is holy and must be
treated with the utmost respect. Code is not allowed to enter the pearly gates
of the main repository until it has been subjected to a
[code review][kiln: code review]. Code reviews aren't scary, in fact they are
one of the fun points of the job. Anyone can perform a code review, however it's
best if [Josh][josh@] is the main reviewer until the development team expands.

To start off a project, create a branch repository from the main one in Kiln.
Name it with YOUR NAME. Done, you're ready to [work on a case](#workingonacase).

#### Working on a Case

A quick workflow for working on a particular feature or bug:

1. Find the relevant case in FogBugz. If no case exists, [bug someone][josh@]
about why a case doesn't exist.
2. Ensure that the case estimate is correct and move the case to the *In
Progress* [kanban column](#kanban).
3. Start time on the case, even if this isn't a client project and it's only
internal.
4. Open up your branch repository and consider creating a new branch for this
case. For major features definitely. For minor changes, maybe not. We use a
convention for naming cases: `NUMBER_some_description`. Branches are prefixed
with the FogBugz case number, then an underscore, then a short description
replacing spaces and non-ascii characters with underscores.
5. Make sure this branch is synced with your branch repository
(`git push -t origin 123_example_branch`).
6. Work and make commits frequently remembering to make a note of the case
number in the commit message. If there isn't a good place to put it, creating a
line at the bottom of the commit message in the form `Ref case NUMBER` is
perfectly acceptable.
7. Push work frequently to your branch repository. It doesn't do a distributed
system any good if your work isn't pushed.
8. Repeat steps 5 & 6 until the feature is complete.
9. Restructure your commit history to your liking. Convention is to rebase your
smaller commits into a few larger more detailed commits ammending the commit
messages to be more detailed.
10. Request a code review of your branch repository.
11. Once the review is complete, merge your code into your master branch and
then your master branch will be merged with the main repository.
12. Resolve the case and assign it to the person in charge of deployments for
that project.
13. Once the new code is deployed the case will be closed.

That's our <strike>12</strike> 13 step workflow for working on a case using
FogBugz and Kiln.

[fogbugz two minutes]: http://help.fogcreek.com/4/fogbugz-in-two-minutes
[fogbugz: ebs]: https://help.fogcreek.com/9121/which-estimates-are-used-by-ebs
[kiln: code review]: http://help.fogcreek.com/8268/code-reviews-in-kiln
[josh@]: mailto:josh@byjakt.com
[ia: new file system]: http://ia.net/blog/mountain-lions-new-file-system/
