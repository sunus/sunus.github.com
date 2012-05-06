---
title: hg branch != git branch
layout: post
categories:
- Tech
tags:
- Git
- Mercurial
- Development
---

In Git, a branch is merely one of the many kinds of ‘refs’, and a ‘ref’ is simply a pointer to a commit. This means that there’s nothing fundamentally different between ‘bob/do-test’ or ‘tmp-do-test’, or ‘master’, they are all pointers to commits, and this pointers can be easily be deleted, renamed, fetched, pushed, etc. IOW you can do pretty much whatever you want with them.

In Mercurial, a branch is *embedded* in a commit; a commit done in the ‘do-test’ branch will *always* remain in such a branch. This means you cannot delete, or rename branches, because you would be changing the history of the commits on those branches. You can ‘close’ branches though. As Jakub points out, these “named branches” can be better thought as “commit labels”.

*From* [Mercurial vs Git; it’s all in the branches](http://felipec.wordpress.com/2011/01/16/mercurial-vs-git-its-all-in-the-branches/)




