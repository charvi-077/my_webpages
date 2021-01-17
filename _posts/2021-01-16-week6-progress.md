---
layout: post
title: Week 6 - Reviews and Discussions
---

Received reviews on the [patch series](https://lore.kernel.org/git/20210108092345.2178-1-charvi077@gmail.com/) sent last week to Git mailing list and also discussed regarding the implementation of next subtask.

## Progress:

For the implementation of the `amend!` commit, firstly after going through the Phillip's patches that implements the `amend!` commit as `git commit --amend=<commit>` I started with looking around the codebase of `builtin/commit.c` and debugging for the variables, functions when we run command `git commit --fixup=<commit>` and spotted for the changes to be done in `prepare_to_commit()`. Then I also spent some time learning about `parse-options` API.

So, the subtask to be done on the top of Phillip's patches is to implement the different user interface of the `amend!` commit considering all pros and cons of the available options. And after discussing with the mentors and community on the git mailing list as [here](https://lore.kernel.org/git/CAPSFM5f+cm87N5TO3V+rJvWyrcazybNb_Zu_bJZ+sBH4N4iyow@mail.gmail.com/), it’s decided to implement it as `git commit --fixup=amend/reword:<commit>`. Also, one of the major features to select this option is that it supports the backward compatibility as guided by Phillip [here](https://lore.kernel.org/git/99b40665-45dd-6c4d-d46a-56c7dbf89568@gmail.com/).
Earlier I started playing around and implementing it in different way, on the [work branch](https://github.com/charvi-077/git/commits/amend-patches/amend-commit-v1) but now after discussions, I got more clear regarding the implementation and working on it.

## TODO:

Still some minor changes are left to be done before sending the v2 of patch series on the mailing list as pushed on the [work branch](https://github.com/charvi-077/git/commits/amend-patches/fixup-patch-v2.1), will complete that. Next, for this week I will continue to work on implementation of the amend!/reword! commit and prepare it's patch series.

#### It’s the middle of the internship and as per project timelines I am running late in completing the first task of `"Implementing reword! commit"`, which could be replaced as `"Add amend! and reword! options to the fixup! commit"`. But I will speed up and complete this task soon. Also, I am thankful for the support from mentors and the community.  

Thanks. 


