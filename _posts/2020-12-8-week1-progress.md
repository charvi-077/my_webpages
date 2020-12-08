---
layout: post
title: Let's get started !
---

My first task in the project is to Implement the `reword!` commit in the git interactive rebase. This would be an alternative to the `fixup!` and `squash!` commit which would allow the user to edit the commit (either commit message or content or both) when they create a `reword!` commit rather than when they rebase. And for the coming weeks I will be working on this task. 

### Work done  
#### I started with the following: 
* Setting up remote repo to push all my changes [here]( https://github.com/charvi-077/git ).
* Completed the My first contribution [tutorial](https://git-scm.com/docs/MyFirstContribution) which made me more clear about the source code and also referred [here](https://git.github.io/Hacking-Git/) for more pointers to get started .
* Setting up this website hosted on [github](https://github.com/charvi-077/charvi-077.github.io), where I will weekly post my updates on the project.

Also, Phillip told me about the [sanitizers](https://github.com/google/sanitizers). I enabled it in my config.mak file and learned about it, so that while building the git repo we can easily detect the address and memory leaks. In addition to this I also enable the warnings and debugging information and my config.mak looks like below :

	DEVELOPER = 1
	CFLAGS = -ggdb3
	SANITIZE = address,leak

Next I spent some time in learning about the advanced linux commands including [pipes in linux](https://www.howtogeek.com/438882/how-to-use-pipes-on-linux/), many other and about the `git internals` from [here](https://github.com/pluralsight/git-internals-pdf/releases/download/v2.0/peepcode-git.pdf). Also, I referred to Pro Git to get more understanding of the git [Plumbing and Porcelain](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain) commands.

Then, after discussing with Christian and Phillip regarding the project and related doubts. Firstly I started with, to have an overview of the Phillip's [patches](https://github.com/phillipwood/git/commits/wip/rebase-amend) which is the starting point of my task as it implements the similar amend! commit.

Then I started learning about the test scripts in the patches and debugged it. All test scripts in the git give the [TAP](http://testanything.org) output and there are a set of helper functions defined in the test harness library (`t/test-lib.sh`) which are used to write the test scripts . Also, I referred to t/README where everything regarding the test scripts are very well documented.

#### Points to consider:
* Use `test_pause` in test scripts to look into the trash directory(which stores temporary data using testing) .
* Pass --verbose(or -v) to see the output if any , --run(or -r) to run the selective tests , -i to exit upon first test fail
* Pass --debug(-d), to run the command passed with `test_debug` in the test script.

Also, I learned about the `t/lib-rebase.sh` where more helper functions are defined, which are used in writing the tests for the interactive rebase and learned about the `set_fake_editor()` function for setting up the fake editor while writing the test scripts.

### Next Plans
I will continue to work on test script, complete tests mentioned in the patches and will look more into the patches, for further changes.

Thanks.
 

