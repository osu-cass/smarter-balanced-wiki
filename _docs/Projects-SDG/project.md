---
title: Smarter Balanced
category: SDG Projects
order: 1
---

## Smarter Balanced Sample Items Repository
> [SampleItemsWebsite](https://github.com/osu-cass/SampleItemsWebsite)

## Project Management

Source Control: Git  
Note on branch management: **Merge** instead of rebasing if the commits to be rebased/merged have been pushed anywhere.

**If you can't build in Visual Studio because of TypeScript errors:**  
Make sure you've updated Visual Studio's TypeScript version. Go [here](https://www.typescriptlang.org/index.html#download-links) and click your Visual Studio version to get the appropriate package.

Project Management: TFS ([Work Items] (http://osu-tfs:8080/tfs/BSGCollection/SB-SampleItemsWebsite/SB-SampleItemsWebsite%20Team/_backlogs#hub=Backlog+items&_a=backlog))

Project Share: ``\\cass-ops\c$\Share\Smarter Balanced\Sample Items Website``

Trello: [Link](https://trello.com/b/5BFs854G/sample-items-website)

MS Project: Google drive share ``CASS-SDG > Clients > Smarter Balanced > Sample Items Share > Project Management > SmarterBalanced Milestones Calendar.mpp ``

## Sites
Branch| Build | Url
--- | --- | --- |
Master | [![Build Status](https://travis-ci.org/osu-cass/SampleItemsWebsite.svg?branch=master)](https://travis-ci.org/osu-cass/SampleItemsWebsite) | [Sample Items Prod](http://sampleitems.cass.oregonstate.edu/)
Stage | [![Build Status](https://travis-ci.org/osu-cass/SampleItemsWebsite.svg?branch=stage)](https://travis-ci.org/osu-cass/SampleItemsWebsite) | [Sample Items Stage](http://sampleitemsstage.cass.oregonstate.edu/)
Dev  | [![Build Status](https://travis-ci.org/osu-cass/SampleItemsWebsite.svg?branch=dev)](https://travis-ci.org/osu-cass/SampleItemsWebsite) | [Sample Items Dev](http://sampleitemsdev.cass.oregonstate.edu/)

##Wireframe
[SampleItemsWebsite-Wireframe](https://github.com/osu-cass/SampleItemsWebsite-Wireframe)

### Milestones
Each milestones will be one three-week scrum sprint. A milestone represents a testable component of the application to be demoed and run through user acceptance criteria upon completion. Each milestone will have a duration of 3 weeks and contain a set of user stories which are to be completed by the end of the milestone. 

Below is the diagram of milestone development:

<img src= "https://cloud.githubusercontent.com/assets/17240077/19093449/1ebc7390-8a40-11e6-9ede-a1486e1240de.png" width= "300" height= "200"/>

### Feature Branches
A git feature branch should be short lived (~2 week max) and represent a stand-alone feature.

### Pull Requests
A pull request represents the completion of a feature branch and corresponds to a user story. 

Before accepting the pull request, the acceptance criteria within the corresponding user story will be evaluated, and a code review will be performed. 
- If the acceptance criteria is met and the code reviewer approves the work, they are to comment `+1` on the pull request. The scrum master will then review the pull request and accept or deny it accordingly.
- If a code reviewer determines that the work is not acceptable or acceptance criteria is not met, they are to comment `-1` along with justifications on the pull request. The team members associated with said pull request are to review and update the feature branch to resolve issues noted by the reviewer. Upon completion, the team members will comment on the pull request to notify the reviewer of the updates, and the review process begins again. 

### User Stories/Requirements
User stories should encompass requirements for a feature. Stories within a milestone should not depend on each other, and should not overlap.

Each user story will have tasks assigned to it, which will be assigned to and completed by members of the development team.


