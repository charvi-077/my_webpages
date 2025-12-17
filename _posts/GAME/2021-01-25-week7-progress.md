---
layout: single
title: Week 7 -  Bug in the patch series & [WIP] Implementation of amend! commit
categories: software_engineering
author_profile: false
tags: ["software engineering"]

---

Last week was spent debugging the patch series, solving bug, addressing the code reviews and also doing some corrections in implementation of amend! commit.

## Progress :
I continued with the implementation of `amend! commit` [work-branch](https://github.com/charvi-077/git/commits/amend-patches/amend-commit-v3.1). Also I got stuck, as I was unable to track the extra commented lines adding to the `amend! commit` message body. After discussing with mentors I got a way out for this. So the reason was that I was setting `use_editor` variable in `prepare_to_commit()` and it gets reset in the `parse_and_validate_options()` function which sets the `cleanup_mode` other than the default one. It was a silly bug but I learned to track the bug and liked the way everything is structured in the codebase. Sometimes it gets difficult to track but it's equally important to write readable and maintainable code and I am learning too. :)

Next, received reviews on the [v2-Patch series](https://lore.kernel.org/git/20210119074102.21598-1-charvi077@gmail.com/). Got some suggestions on documentation and to add the additional tests for multiple `fixup -c` sequences in interactive rebase, to check if it opens the editor once. And here I will not forget to mention that there was a minor bug in the patch series as it was failing to open the editor for sequence `fixup -c` `fixup -C`. Next, other changes suggested in the patch series is to simplify the `subject_length()` function previously written by Phillip, I learned a way out after discussions and also to do some corrections in the `t3415-rebase-autosquash.sh` and I also admit that this time I mistook some reviews, maybe unable to think the other way and thanks Christian and Phillip for correcting me. After doing all these changes, sent the [v3-Patch series](https://lore.kernel.org/git/20210124170405.30583-1-charvi077@gmail.com/) to the mailing list.

## TODO:
This week I will continue to complete the patch series of `amend!` and `reword!` commit. Coming to implementation of `reword!` commit, some rethinking need to be done for its `User interface` as there are two possibilities :
1. make a `reword!` commit, using `git commit --fixup=reword:<commit>` and upon autosquash it will change pick command to `fixup -C` (not changing to present command `reword` as we don't want editor to be opened again)
2. make `amend!` commit, using `git commit --fixup=reword:<commit>` and upon autosquash it will change pick command to `fixup -C`.

So here both only reword any previous commit and it implies `--allow-empty`. Any suggestions for `reword!` commit user interface?

Thanks for reading.

