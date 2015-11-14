---
layout: post
title: Rewriting author name for all commits
---

I recently discovered I was making commits for a project with the wrong author
name and email.  I had made several commits on one branch and needed to change
all of them.  One command did the trick.

    git filter-branch -f --env-filter "
        GIT_AUTHOR_NAME='Jefferson Carley'
        GIT_AUTHOR_EMAIL='jeff.carley@gmail.com'
        GIT_COMMITTER_NAME='Jefferson Carley'
        GIT_COMMITTER_EMAIL='jeff.carley@gmail.com'
      " HEAD

This command is not merciful.  It will change the author of every single commit,
basically rewriting the history.  Use this with caution.  If you have several
authors commiting to a branch, you might want to look else where.
