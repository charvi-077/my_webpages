---
layout: post
title: Week 11 - Updates!

---

Received reviews on the previous patch series and continued working on the `Implementation of "drop!" commit`.

## Progress:
Worked on the reviews received on the previous patch series [Implementation of "amend!" commit](https://lore.kernel.org/git/CAPSFM5fL3_pkMNBYSXiRHzbqOwzA0SBH3NjU+zVq3Mxv7UgL4w@mail.gmail.com/T/#m72ee5cbf7bcff22788912a02849acf18cc82fb32) (Thanks to Junio for the suggestions). Firstly, we need to improve the implementation of parsing `fixup_message` to detect `amend`/`reword`, so instead of checking if ':' occurs before '^' or '@', Junio suggested to add helper function that does strspn(alpha). Secondly, to remove '-m' commit message option working with `amend` and `reword` suboptions, here I agree with Junio's point that it is more expected to edit the original commit message while preparing "amend!" commit and using `-m` for directly appending the commit message may result in the confusion at the user end.
Next, there was a bug with `reword` option that was taking changes when passed with `pathspec`, or with `interactive_patch` options. So we need to add a check and error it out. Besides this there were few changes required in commit message and to update the documentation of `git-commit` with above mentioned changes and also to mention about the authorship of the fixed up commit.

###### Revised patch series:
[v2 - Implementation of "amend!" commit](https://lore.kernel.org/git/20210225100855.25530-1-charvi077@gmail.com/T/#u)

Next, started working on the "drop!" commit patch series [workbranch](https://github.com/charvi-077/git/commits/drop-patches/drop-commit). Till now we are able to create the "drop!" commit using command `git revert --drop`. And, coming to the working of "drop!" commit upon `--autosquash`, it is currently resulting in segmentation fault, maybe we need to add check if "drop!" commit is rearranged or not in rebase todo-help and still I am working on it. Next, as pointed by Phillip we also need to look for the working of the chain of the "drop!" commits, which I think to check for commit subject starting with "drop! drop" as in this case we don't need to change the command of previous commit from `pick` to `drop` in rebase todo-list...Work still in progress...

###### Some related Light readings:
- `git reset` vs `git revert`, [link](https://www.freecodecamp.org/news/the-ultimate-guide-to-git-reset-and-git-revert/).
- How to revert a merge commit in git, [link](https://www.johbo.com/2016/how-to-revert-a-merge-commit-in-git.html).

## Todo:
Will continue to work on the "drop!" commit patch series that includes to solve the bug, complete the working of "drop!" commit upon --autosquash and to add the tests and documentation for the same.

Thanks for reading!


