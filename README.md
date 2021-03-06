# git-bisect-demo

This is a dummy repository to demo how `git bisect` works. The repository contains a spelling mistake (try to spot it!) that it is introduced during the writing of this README and `git bisect` will help us finding when the bug was introduced in the code base.

## Description 

`git bisect` is a powerful Git command that can help you finding bugs in your code. It uses a binary search to find the commit that introduced a bug in your code.

This command uses a binary search algorithm to find which commit in your project’s history introduced a bug. You use it by first telling it a "bad" commit that is known to contain the bug, and a "good" commit that is known to be before the bug was introduced. Then `git bisect` picks a commit between those two endpoints and asks you whether the selected commit is "good" or "bad". It continues narrowing down the range until it finds the exact commit that introduced the change.

In fact, `git bisect` can be used to find the commit that changed **any** property of your project; e.g., the commit that fixed a bug, or the commit that caused a benchmark’s performace to improve. To support this more general usage, the terms "old" and "new" can be used in place of "good" and "bad", or you can choose your own terms.

## Basic bisect commands: start, bad, good

As an example, suppose you are trying to find the commit that broke a feature that was known to work in version `v2.6.13-rc2` of your project. You start a bisect session as follows:

```
$ git bisect start
$ git bisect bad                 # Current version is bad
$ git bisect good v2.6.13-rc2    # v2.6.13-rc2 is known to be good
```

Once you have specified at least one bad and one good commit, `git bisect` selects a commit in the middle of that range of history, checks it out, and outputs something similar to the following:

```
Bisecting: 675 revisions left to test after this (roughly 10 steps)
```

## References
[Git documentation](https://git-scm.com/docs/git-bisect)
