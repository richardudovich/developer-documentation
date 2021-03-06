---
category: Develop
---
# The Core Team Workflow

## About this guide

This guide describes how we, the team of developers that makes changes to Piwik Core, operate and how others can participate in our work.

**Read this guide if**

* you'd like to know **how the core team works**
* you'd like to know **how to reach the core team**
* you'd like to know **how to submit a bug report or feature request**
* you'd like to know **how to take part in core development by submitting a pull request**

**Guide assumptions**

**This guide makes no assumptions.** You do not need to know how to code or know how Piwik works in order to understand this guide.

## How we manage our work 

We use **[Github](https://github.com/piwik/piwik/issues)** to keep track of all bugs, feature requests and tasks that concern Piwik, the website and Piwik's documentation.

We make sure all tickets contain enough information, including:

* if a bug, details regarding how to reproduce it,
* if a new feature, explain the use case with suggestions or a specification,
* if a UI improvement, mockups or a detailed description of the changes.

We are rather obsessed with keeping our issue tracker an organized place. 
Tickets are generally prioritized by severity. 
Tickets are either of the type 'Bug', 'Enhancement' or 'Task'. 
All Bugs are moved to the current milestone because of our [no-bug policy](http://piwik.org/roadmap/). 
Developers (Piwik team members or external contributors) decide for themselves which features they would like to work on.
We have been using an issue tracker since [the beginning of the project](http://piwik.org/history/). 

## How we organise issues

### Milestones 
All opened tickets are grouped in [Milestones](https://github.com/piwik/piwik/issues/milestones). Click the menu link 'Milestones' [in github issues](https://github.com/piwik/piwik/issues). 
The versions milestones are listed at the very top and contains all the most important issues to close in accordance with [our vision for the Piwik analytics platform](http://piwik.org/roadmap/).

Very important issues and all bugs are moved to [Short term milestone](https://github.com/piwik/piwik/milestones/Short%20term). 
This milestone is our active tickets backlog. From time to time, we move one ticket from `Short term` to the current version milestone (eg. `Piwik 3.0.0`).

Other suggestions, tasks and feature requests which we haven't yet scheduled are moved to the [Mid term](https://github.com/piwik/piwik/milestones/Mid%20term) or [Long term](https://github.com/piwik/piwik/milestones/Long%20term) milestones.

### Labels
Most important labels are tagged to issues: 
[Privacy](https://github.com/piwik/piwik/labels/c:%20Privacy), 
[Security](https://github.com/piwik/piwik/labels/c:%20Security), 
[Performance](https://github.com/piwik/piwik/labels/c:%20Performance), 
[Tests & QA](https://github.com/piwik/piwik/labels/c:%20Tests%20&%20QA), 
[Usability](https://github.com/piwik/piwik/labels/c:%20Usability), 
[Platform](https://github.com/piwik/piwik/labels/c:%20Platform),
[Marketplace](https://github.com/piwik/piwik/labels/c:%20Marketplace) and
[Website piwik.org](https://github.com/piwik/piwik/labels/c:%20Website%20piwik.org). 

Other important labels used are for [Critical](https://github.com/piwik/piwik/labels/Critical) and [Major](https://github.com/piwik/piwik/labels/Major) issues. 
New developers can quickly make an impact by hacking on an [Easy pick](https://github.com/piwik/piwik/labels/Easy%20pick) issues.

## How we release new versions

### Frequent releases
We try to publish a new Piwik release [about once a month](http://piwik.org/faq/new-to-piwik/faq_18926/). A release is ready when the following release conditions are met: 

- Our [continuous integration tests](http://piwik.org/qa/) must be green.
- All critical tickets [to the corresponding milestone](https://github.com/piwik/piwik/issues/milestones) must be closed. 
- All [officially supported plugins](http://plugins.piwik.org/developer/piwik) (built by Piwik) available on the [Marketplace](http://plugins.piwik.org/) must be compatible.

Generally we will release several beta releases to give early access and ensuring continuous testing of Piwik.

To publish a new Piwik version, the release manager will tag the new version in git (see [all release tags](https://github.com/piwik/piwik/tags)). 
A shell script is then run to generate the archives (zip and tar.gz) which are [cryptographically signed](http://piwik.org/blog/2014/11/verify-signatures-piwik-packages/) and then copied to the build server [builds.piwik.org](http://builds.piwik.org/) and [builds.piwik.org/LATEST](http://builds.piwik.org/LATEST) is updated with the latest stable release number. 
Within hours, Piwik installations will be updated by users via the one click [upgrade mechanism](http://piwik.org/docs/update/) &ndash; or by manual upgrades.

Releases that contain the string "alpha", "beta", "rc", are built for testing purposes and are not advertised on [piwik.org](http://piwik.org).
They are however made available on the build server and the [builds.piwik.org/LATEST_BETA](http://builds.piwik.org/LATEST_BETA) is updated to contain the release's version string. 
You can enable Piwik to use the latest Beta release automatically if you want to test the latest features ([see this faq to learn how](http://piwik.org/faq/how-to-update/#faq_159)).

### Changelog

The [Changelog](http://piwik.org/changelog/) is then updated with a new entry for this release. 
The changelog typically lists all tickets closed in this release, and point people to the newest [FAQs](http://piwik.org/faq/) and [User guides](http://piwik.org/faq/).

## How we manage source code

The Piwik git repository is hosted at [Github](https://github.com) and is publicly accessible at [https://github.com/piwik/piwik](https://github.com/piwik/piwik).

As of 2014, we manage [over fourty repositories at Github](https://github.com/piwik). This includes the [main repository for Piwik](https://github.com/piwik/piwik) and several plugins, themes, and toolsets to make the most out of Piwik, such as Piwik clients for software development in Python, Ruby, C#, SDKs for iOS, debian packages and other useful Piwik developer tools.

In case Github goes down, we maintain a backup Git Mirror at: [git.piwik.org](http://git.piwik.org).

#### Git Owners

All developers from the Piwik organization can push to all git repositories.

#### Git mailing list

This mailing list notifies all the commits to our [Git repository](https://github.com/piwik/piwik): [Archives](http://lists.piwik.org/pipermail/piwik-git/), [Subscribe](http://lists.piwik.org/cgi-bin/mailman/listinfo/piwik-git), [Search the archives](http://www.google.com/coop/cse?cx=012634963936527368460%3Afzsqvqnvzoi).

#### Git commit process

All code committed to git is reviewed by at least one other developer in the team. Very often, Piwik developers themselves will send bigger changes by pull request for review before committing. All pull requests or patches submitted by external developers are extensively reviewed.

It is highly recommended that code committed in the [master branch](https://github.com/piwik/piwik) respects the [Piwik coding standards](http://piwik.org/participate/coding-standards), does not cause tests to fail, and does not create regessions in the UI or the platform. And the commit message should reference a ticket number in almost all cases; for example,

    fixes #159 - changed patch to use wrapInner() instead of wrap()

This message will automatically close the ticket [#472](https://github.com/piwik/piwik/issues/472). 
You can also use simply `#159` and a comment will be automatically added to the ticket #159 with a link to the commit on Github.

When applicable, the related [online documentation](http://piwik.org/docs/) and the related [FAQs](http://piwik.org/faq/) should be updated.

## Getting in touch with Core Team

### In the forums

Join us in the forums at [forum.piwik.org](http://forum.piwik.org)

Discover our vibrant community where analytics tips are shared, suggestions on how to make the most out of Piwik, or general questions. Several team members visit the forums regularly, as well as active members of the community.

### By email

You can contact the team by email: <a href='mailto:hello@piwik.org?subject=Contact the Piwik team'>hello (at) piwik.org</a>, or using [the contact form](http://piwik.org/contact/).

### Using IRC

Some team members may be available in IRC at [irc.freenode.net/#piwik](irc://irc.freenode.net#piwik) ([webchat](http://webchat.freenode.net/?channels=piwik&uio=MTE9NTE3a)).

## Influencing Piwik development

There are many ways you can make a difference in the project and influence the overall goodness of Piwik, most of which do not include coding.

### Comment on existing issues

If you find a new feature request very exciting or important, or if you're experiencing a particular bug, the best way to be heard by the Piwik team is to comment on the ticket. Features that are most requested are often higher on the priority list.

### Submitting a bug report

One way to help core development is to submit a report when you find a bug.

If you believe you have found a bug in Piwik, please do the following:

* make sure you are using the latest [Piwik release](http://piwik.org/download/)
* search in the [forum](http://forum.piwik.org/), [FAQ](http://piwik.org/faq/) and the [issue tracker](https://github.com/piwik/piwik/issues) if a similar or the same bug has already been reported.
* if your bug seems new, try to identify the steps to reproduce it.
* if you are ready to report a bug, register an account [in the issue tracker](https://github.com/piwik/piwik/issues), login and [create a new ticket](https://github.com/piwik/piwik/issues/new)
* make sure the title and description are as descriptive and clear as possible. Is the issue new to you, or has it always failed? If you give a clear description, you will help developers trying to reproduce and fix the issue.
* in the ticket, post instructions on how to reproduce the bug, add data sets if applicable, screenshots. Also include details about relevant parts of your configuration (browser, OS, PHP version, etc.).

### Submitting a feature request

Another way to contribute is to submit a feature request.

You can tell us what we can do to improve Piwik in the [Feature Suggestions forum](http://forum.piwik.org/index.php?showforum=3). Please check that it is not already in the [list of Piwik tickets](https://github.com/piwik/piwik/issues).

When submitting a significant new feature, it is recommended to be as descriptive as possible. The ticket should contain:

- a description of the product vision
- a few use cases to show how useful this feature would be
- mockups of what the new screens would be and how the existing screens would have to change
- if applicable, examples of how the feature is implemented in other existing tools

Please put as much information as possible as it will help to estimate the effort needed (by the Piwik core team or by a Piwik consultant). We will help with any technical details and questions outlined in the ticket.

### Contributing code

And of course if you can code and want to directly help Piwik development, you can contribute changes. To learn about contributing code changes, read our [Contributing to Piwik Core](/guides/contributing-to-piwik-core) guide.

## How do I become an official Piwik team member?

All [Piwik team members](http://piwik.org/team/) have contributed major improvements to the project. They have contributed their talent towards our common goal of building the best open analytics platform. Some of these achievements were feats of engineering, as documented on our [blog posts](http://piwik.org/blob/) over the last few years.

To gain push access to our git repository, and be an official Piwik team member, one must make positive changes in the project, such as  [contributing pull requests](http://developer.piwik.org/guides/contributing-to-piwik-core), bringing new ideas, code, marketing, product visions. When a certain amount of work has been achieved, when we trust your skills and judgement, we will invite you to [join us in the core team](http://piwik.org/team/). Most of us also meet once a year in a beautiful European city for brainstorming the future of analytics, open source, [privacy](http://piwik.org/blog/2014/01/data-privacy-day-january-28th/) and Piwik.

There are other useful ways to participate to Piwik without joining the team, learn more: [How do I get involved?](http://piwik.org/get-involved/)

