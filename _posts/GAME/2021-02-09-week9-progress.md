---
layout: single
title: Week 9 - Modifications
categories: software_engineering
author_profile: false
tags: ["software engineering"]

---

U TURN in the project and worked on further improvements required in the previous patch series.

## Progress:
Last week received some more suggestions on the [v4-patch series](https://lore.kernel.org/git/20210129182050.26143-1-charvi077@gmail.com/), which includes removing a bug - need to fix datatype of `flag` argument as it was used as `combination of bits` but was declared as `enum todo_flag_items`. Next it includes some fixes in the commit messages, updating the test script `t3437` and `lib-rebase.sh` and some other minor fixes (Thanks to Eric Sunshine for the detailed reviews). After discussing with the mentors and on the mailing list, I updated the patches and sent a [v5-patch series](https://lore.kernel.org/git/20210204190507.26487-1-charvi077@gmail.com/). Oops, that was a mistake!

Here I will mention to **keep track** of the patches in "What's cooking" frequently sent by Junio to the mailing list.

Now as the v4-patch series was already merged to next branch so v5 revision was of no use as changes were done with interactive rebase and instead it is required to be done incrementally on the top of merged branch [Instructions](https://git-scm.com/docs/MyFirstContribution#after-approval).

#### Command to find the tip of what got merged in "next" :

"`git log --first-parent --oneline master..next`"

(Thanks to Junio for guiding in detail as [here](https://lore.kernel.org/git/xmqqmtwi1g6u.fsf@gitster.c.googlers.com/))

So, this time sent a new patch series [Patches-Improve the fixup [-C -c] in interactive rebase](https://lore.kernel.org/git/20210207181439.1178-1-charvi077@gmail.com/) built incrementally that includes the changes of v4-patches and also some additional changes in the test script suggested by Phillip. Also received some more reviews on that and worked on updating those, below is the link of the latest patch series sent on the mailing list :

**Patches:** [V3-Patches-Improve the 'fixup [-C -c]' in interactive rebase](https://lore.kernel.org/git/20210210113650.19715-1-charvi077@gmail.com/)

Also, while working on the reviews I got stuck and wondered _How to make different commits for different changes in the same file ?_ After discussing with mentors I got way out and learned about the `git add -p`, [git patch mode](https://johnkary.net/blog/git-add-p-the-most-powerful-git-feature-youre-not-using-yet/) which is a really very powerful command. Besides this another common issue is _How to undo a git rebase ?_ Hint: use git reflog and git reset [Read More..](https://gunnariauvinen.com/how-to-undo-a-git-rebase-and-recover-hours-of-work/) Also, I learned that `git reflog branch_name` usually eases out the things in comparison to the `git reflog` which outputs the `HEAD reflog`.

## TODO:
Will continue to work on some more improvements in the next patch series (to be sent on the mailing list) of implementation of `amend! commit` and [here](https://github.com/charvi-077/git/commits/amend-patches/amend-commit-v3.5) is the latest `work-branch` of it.

Thanks for reading !
