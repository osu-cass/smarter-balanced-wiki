---
title: Seed Analysis
category: SDG Projects
order: 1
---
## Seed Analysis Repository
> [Seed Analysis](https://github.com/osu-cass/SeedAnalysis)

### Meta
- State: development
- Point people: 
[@rutgerfarry](https://github.com/rutgerfarry), 
[@EvanSchallerer](https://github.com/EvanSchallerer)
- CI: [![Build Status](https://travis-ci.com/osu-cass/SeedAnalysis.svg?token=q53GFySHMzZxAw1qNaQ4&branch=master)](https://travis-ci.com/osu-cass/SeedAnalysis)

## Introduction
An iPad app allowing the [OSU Seed Lab](http://seedlab.oregonstate.edu/) to quickly submit test information on their [seed purity tests](http://seedlab.oregonstate.edu/testing-purity).

## Getting started
You'll need a few tools before getting started. Ensure you have a recend copy of Xcode downloaded. Then run the following two commands to install `bundler` and the Xcode command-line tools, if you don't have them yet.
```sh
[sudo] gem install bundler
xcode-select --install
```

Then, to download the code, run the following lines. We use some Ruby and Swift dependencies; the following commands ensure they're downloaded and hooked into the Xcode workspace.
```sh
git clone https://github.com/osu-cass/SeedAnalysis.git
cd SeedAnalysis
bundle install
bundle exec pod install
```

## Contributing
### Commit Messages
Commit messages should be 2 lines. The first line should be a short overview, and the second containing TFS work item Ids, such as below:
```
Completed work on back-end feature, fixed bug in some related feature.
TFS work items XXXXX, XXXXX, and XXXXX.
```
### Branches
Three permanent branches are used, `master`, `stage`, and `dev`.

Other branches are to be named `feat-<feature-name>`.

### Pull-request etiquette
Before making a pull-request, ensure tests are passing locally and that the Xcode project structure is synced with the on-disk file structure (Xcode doesn't do this automatically). This can be accomplished with these two lines:
```sh
bundle exec fastlane test
bundle exec fastlane synx
```