---
layout: single
title: Week 10 - Patch Series Sent & [WIP] Implementation of "drop!" commit
categories: software_engineering
author_profile: false
tags: ["software engineering"]
---

Last week I spent on stitching up the loose points in the prepared patches of "amend!" commit ([workbranch](https://github.com/charvi-077/git/commits/amend-patches/amend-commit-v3.7)) and finally sent it to the mailing list. After that also started with the second part of project i.e to Implement the "drop! commit".

## Progress:
In "amend!" commit patch series, worked on adding a check so that git deny to create "amend!" commit if the commit message body of "amend!" commit is empty. Further as suggested by Phillip, added an additional check so that it allows to create the “amend!” commit with an empty commit message body if `--allow-empty-message` is passed with it and also updated the tests for the same (t/t7500). Besides this, worked on some more improvements in documentation and commit messages as guided by Christian and Phillip.


###### Patches Status :

###### Latest Patches (Under Review) : [commit: Implementation of "amend!" commit](https://lore.kernel.org/git/20210217072904.16257-1-charvi077@gmail.com/#R)

###### On Seen Branch (topic:cm/rebase-i-updates) : [Improve the 'fixup [-C | -c]' in interactive rebase](https://lore.kernel.org/git/20210207181439.1178-1-charvi077@gmail.com/)

###### On Next Branch (topic:cm/rebase-i) : [rebase -i: add options to fixup command](https://lore.kernel.org/git/20210129182050.26143-1-charvi077@gmail.com/)

Next, Implementation of "drop!" commit, that addresses the issue as [here](https://github.com/gitgitgadget/git/issues/259). It's working includes - to create a "drop! commit" and also dropping the changes of the specific commit (i.e now done using [`git revert <commit>`](https://www.atlassian.com/git/tutorials/undoing-changes/git-revert)). So, we can go with the suggested **UI** as below:

`git revert --drop <commit>`

that mirrors the below commands:

`git revert -n <commit> &&`

`git commit -m 'drop! '"$(git show -s --oneline <commit>)"`

Also upon `git rebase --autosquash`, it will implicitly drop the specific commit and the "drop!" commit as well.

Starting with the implementation I started with looking around and debugging into the `revert.c` file where we need to add the `--drop` option. Then traced the functions and figured out the `do_pick_commit()` in `sequencer.c` where we need to add the functionality of "drop!" commit and to modify the `replay_opts` structure to add `--drop` option. And the further work is still in progress.

Besides this I was also looking for **How to fetch the complete series of patches at once from the mailing list ?**

One way to fetch is to download the raw patches from the mailing list and use `git am`.

Alternative, as suggested by Christian I learned about [b4](https://people.kernel.org/monsieuricon/introducing-b4-and-patch-attestation), that work with code submissions in a [public-inbox](https://public-inbox.org/) archive and makes more easier to fetch the complete patch series using single command : 

`b4 am <message-id>` - Create an mbox file of complete patch series that is ready to `git-am`.

**To-Install** - Just Clone the b4 repo from [here](https://git.kernel.org/pub/scm/utils/b4/b4.git/) and follow the README.

**Link to** - [Documentation](https://pypi.org/project/b4/)

## TODO :
Will continue to work on adding a new feature of "drop!" commit and in parallel work on the reviews or any suggestions on the "amend!" commit patch series.

Thanks for reading!
