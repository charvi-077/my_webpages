---
layout: post
title: Week 3 & 4 - Digging into interactive rebase codebase 
---
I started with, finding the answers of what happens when we run `git rebase -i` ? How does the code work after we edit the `git-rebase-todo` ?

So, I spent some time navigating the code, looking into definitions and the data structures used in the codebase. And it becomes more easy after setting up proper keybindings in the [vscode](https://code.visualstudio.com/), using [ctags](https://marketplace.visualstudio.com/items?itemName=jaydenlin.ctags-support) and [GDB](https://www.gnu.org/software/gdb/).

As an overview, the very first entry point is `main()` function in `comman-main.c`, following the `cmd_main()` in `git.c`. Then in builtin folder, there is  `rebase.c` which consists the two functions `cmd_rebase()` and `cmd_rebase__interactive()` which are the entry points for the git rebase command which further calls `run_sequence_rebase()` and `sequencer_continue()`. 
 
Next, after discussing with Phillip and Christian more regarding the patches and codebase I learned about the `sequencer.c` codebase that handles the working of git-rebase-todo, where entry point is `sequencer_continue()`, which calls `read_populate_todo()` to read the todo list and then calls `pick_commits()` to pick the commits, `pick_commits()` then loops through the todo list and picks each commit by calling `do_pick_commit()`.


## Progress

As started earlier, I completed the modifications in the test scripts as [here](https://github.com/charvi-077/git/commits/amend-patches/test-script-v6), but it still need to be changed simultaneously with the changes in the Phillip's patches.
Next, after poking around the codebase I started working on changing the amend patches as [here](https://github.com/charvi-077/git/commits/amend-patches/fixup). So, I removed the amend command from the current Phillip's patches and added the options to the fixup command in the interactive rebase.
And changing pick command to the respective one, will work as described below:

- `fixup`, work like squash but remove this commits log
- `fixup -C`, work like squash but replace above commit's message with this commit message.
- `fixup -c`, work like squash, replace above commit's message with   this commit and also open the editor to edit.

#### Points to consider:
- run interactive rebase with [`--rebase-merges`](https://jnielson.com/git-rebase-with-merges), in order to save your merge commits
- `.git directory`, that stores all the information
- look around the [strbuf API](https://schacon.github.io/git/technical/api-strbuf.html)
- git supports so many languages, look around [gettext](https://www.gnu.org/software/gettext/)

## TODO
I will complete the modifications required in the patches as guided by Christian, which is in [progress](https://github.com/charvi-077/git/commits/amend-patches/fixup). Next, I need to look into its working if the commit messages are empty and will also complete the changes in the test script in accordance with the fixup command options in interactive rebase.

PS: Last week I worked less, but will try to speed up and send the patch series to the mailing list asap.

Thanks &
Happy New Year, 2k21

