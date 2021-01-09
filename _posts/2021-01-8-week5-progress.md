---
layout: post
title: Week 5 - Patches for adding options to the fixup command. 
---

Writing CLEAN CODE - CLEAN PATCHES - that are easily readable and maintainable is also an essential part. So, this week is spent mostly on fixing up the commits, commit messages, making preparatory/clean-up patches and debugging for more changes.

## Progress

Following last week, I continued with fixing up the commits that implements the `fixup -C` and `fixup -c` commands. After that, I started with updating the test script and replacing the `amend` command on which we worked earlier, with the `fixup -C` command. But I got stuck at parsing the multiple word command i.e `fixup -C` in `lib-rebase.sh`. I discussed with Phillip and Christian and got a pointer to make additional case for `merge` and `fixup` options in lib-rebase.sh. Then I debugged the code again and did some changes as two tests were failing with `fixup -c` and also added a new test case for `fixup -c` command.

Next, as guided by Christian I also split some commits and added those changes in the preparatory patches. After that added additional commits and tests for the working of `amend!` commit upon `--autosquash`, following Phillip's patches.

Then after doing all the changes in the code base, tests and documentation one of the important steps before sending the patches to the mailing list, is to write the `cover letter` explaining the reason and use of patches, wrote that and did the changes as guided by Christian and Phillip.

#### Git commands for preparing patches:
- [`git format-patch`](https://devconnected.com/how-to-create-and-apply-git-patch-files/), for preparing patches for email submission and include --cover-letter for adding the cover letter.
- [`git send-email`](https://riptutorial.com/git/example/16977/use-git-send-email-with-gmail), for sending a collection of patches as email instead of pull requests and setting up `gmail` as the smtp server.
- [`git am`](https://devconnected.com/how-to-create-and-apply-git-patch-files/), for applying a series of patches from mailbox and its good practise to test and apply patches locally before sending it to the mailing list.

## Patch series sent :
Finally the [patch series](https://lore.kernel.org/git/20210108092345.2178-1-charvi077@gmail.com/T/#t) with RFC sent to the mailing list. And the work branch can be found [here](https://github.com/charvi-077/git/commits/amend-patches/fixup-patch-v1).

## Todo
For the coming week, next task includes:
- Debug and look into the code base of `commit.c`, to find a way out for implementing `amend! commit` and discuss on the mailing list regarding the UI.
- Look around the current implementation of Phillip's patches of `amend! commit`, which implements it as `git commit --amend=<commit>`.
- Work on the reviews and suggestions on the patch series, sent on the mailing list.

Thanks.
