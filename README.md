# git-bisect-demo

This is a dummy repository to demo how `git bisect` works.

`git bisect` is a powerful Git command that can help you finding bugs in your code. It uses a binary search to find the commit that introduced a bug in your code.

This command uses a binary search algorithm to find which commit in your project’s history introduced a bug. You use it by first telling it a "bad" commit that is known to contain the bug, and a "good" commit that is known to be before the bug was introduced. Then `git bisect` picks a commit between those two endpoints and asks you whether the selected commit is "good" or "bad". It continues narrowing down the range until it finds the exact commit that introduced the change.


