---
layout: post
title: Week 2 - Updates
---
Working on `git` using `git`. And it's true that we can't just avoid the `conflicts`. Although, `git` makes the merging or integration of code from different branches very easy and handles itself but there are many situations in which it results in merge conflicts and at that time it is required to be solved manually. 

The most common case is when there is a change in the same file at the same line in  two different branches and if we merge these two branches, then git can't decide which line to keep and mark the conflict in the file and we need to resolve that manually. So keep calm, dig deep and solve the conflicts.

## Progress :
This week, I also got messed up with merge conflicts but the only way out is to deal with it. I looked into tests written and discussed with Phillip regarding the previous written tests (in `t3437-rebase-amend.sh`) as I got stuck with those conflicts defined in the test script. Also I found `diff3` conflict marker, very useful to solve the conflicts easily as it tells about the common ancestor of the merge also. I looked into detail from [here](https://www.git-scm.com/book/en/v2/Git-Tools-Advanced-Merging). We can easily regenerate the conflict marks in the file, which gives the conflicting error to be solved manually (`git checkout --conflict=diff3 file-name`) or can set `diff3` as default config style (`git config --global merge.conflictstyle diff3`). Also Christian guided to break the large patch series into the smaller one and work on different features in different branches which is also helpful to reduce the conflicts.

#### Some more points to consider :
- use `git rebase -i`, [interactive rebase](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History) to rewrite the commit history but preferred for local changes only.
- `git reflog`, which saved me many times, using this we can easily move back and forth in git history and can even easily undo the git reset.
- use `git cherry-pick` to move commits from one branch to another.
- customize the output of `git log`, use [pretty formats](https://www.git-scm.com/docs/git-log).

Next, I spent some time learning about the shell scripts from [here](https://www.kau.edu.sa/files/830/files/60761_linux.pdf ) as it made me more clear about the functions used in the test libraries (`test-lib.sh`, `test-lib-functions.sh` and `lib-rebase.sh`). I have completed the todo tests (to check if first amend commented out in sequence fixup amend amend). Also as guided by mentors I am working on some modifications required in the test script. Next I have also started looking into the `sequencer.c` and `rebase-interactive.c` and currently going through the changes done in the patch files (to add new command rebase in the patches) to collect some pointers.

## Next Plans
I will complete the modifications required in the test script and will work on changing the `fixup` command in interactive rebase to have options of `-c` and `-C`.  

Thanks.
