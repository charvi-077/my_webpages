---
layout: single
title: Week 8 - Preparation of next patch series!
categories: software_engineering
author_profile: false
tags: ["software engineering"]

---

Last week I spent on preparing the patch series, for the implementation of amend! commit ([work-branch](https://github.com/charvi-077/git/commits/amend-patches/amend-commit-v3.5)) and about to send it on the mailing list.

Currently we already have `fixup!` and `squash!` in git that works with `--autosquash` ([quick reading](https://fle.github.io/git-tip-keep-your-branch-clean-with-fixup-and-autosquash.html)) and implementing the `amend!` serves the other flavour for fixing the commit. So, for that we are proposing for adding two suboptions to `git commit --fixup` and both will create the `amend! commit` and works with `--autosquash` as below:

* `git commit --fixup=amend:<commit>`

It creates an `amend! commit` and allows to edit the commit message and upon rebasing  with `--autosquash` it will fixup the contents and replace the commit message of `<commit>` with the `amend!` commit's message body.

* `git commit --fixup=reword:<commit>`

It creates an `empty amend! commit` that only allows to edit the commit message and will not take any staged changes and when it is rebased with `--autosquash` it will reword the `<commit>`.

## Progress:
I continued with doing the changes for `amend` option as suggested by Christian and Phillip. Next, adding `reword` option is also similar but here it will not take any staged changes and adding some extra flag checks for `reword` option in function parse_and_validate_options() in `builtin/commit.c`. Currently `--fixup` with options only supports the `-m` option. Maybe we can extend it by allowing `--reset-author` but for now it's on halt. Then, worked on adding the tests(`t/t7500-*.sh`) and updating the documentation(`git-commit.txt`) for the `--fixup` with `amend` and `reword` option.

Besides this, I also usually read the [`Git Rev News`](https://git.github.io/rev_news/rev_news/), in which my favourite part is the Developer interviews, that I always enjoy reading and is a pill of inspiration.

## Next:
My plan for this week is to start with the second part, implementation of the `drop! commit` and also in parallel work on the reviews or community suggestions, after sending the complete patch series which includes adding `fixup[-C | -c]` options in interactive rebase and implementation of `amend! commit` to the mailing list.

Thanks for reading!
