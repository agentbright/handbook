---
description: A guide for programming
---

# Git Protocol

## Create an issue branch

Create a local issue branch based off master.

The branch name format should be `<issue number>-<short-description-of-issue>`

```text
$ git checkout master
$ git pull
$ git checkout -b 3254-fix-sequences-ordering
```

Rebase your code frequently to incorporate upstream changes

```text
$ git fetch origin
$ git rebase origin/master
```

Resolve conflicts. When feature is complete and tests pass, stage the changes

```text
$ git add --all
```

When you've staged the changes, commit them.

```text
$ git status
$ git commit
```

Write a good commit message. Format:

```text
#3425 - <Present tense summary of commit>

- Add thing to fix thing
- Add other thing
- Change thing to new thing
```

When you are ready to share your branch, if you have created more than one commit, use git rebase to interactively squash them into cohesive commits with good messages:

```text
$ git rebase -i origin/master
```

Push your branch to GitHub

```text
$ git push
```

## Submitting a Pull Request

We use hub to convert our issues into Pull Requests.

When you are ready to submit your branch for review, after the branch is pushed to GitHub, convert the issue to a pull request:

```text
$ hub pull-request -i <issue number>
```



