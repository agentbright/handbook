---
description: Our workflow for creating and pushing code
---

# Git Protocol

## Creating an issue branch

Create a local issue branch based off master.

The branch name format should be `<issue number>-<short-description-of-issue>`

```text
$ git checkout master
$ git pull
$ git checkout -b 3254-fix-sequences-ordering
```

## Rebasing your code

Rebase your code frequently to incorporate upstream changes

```text
$ git fetch origin
$ git rebase origin/master
```

Resolve conflicts

## Committing changes

When feature is complete and tests pass, stage the changes

```text
$ git add --all
```

When you've staged the changes, commit them.

```text
$ git status
$ git commit
```

Write a good commit message. Here is the format we follow:

```text
#3425 - <Present tense summary of commit>

- Add thing to fix thing
- Add other thing
- Change thing to new thing
```

## Push to GitHub

When you are ready to share your branch, if you have created more than one commit, use git rebase to interactively squash them into cohesive commits with good messages:

```text
$ git rebase -i origin/master
```

Push your branch to GitHub

```text
$ git push
```

## Submitting a pull request

We use hub to convert our issues into pull requests.

When you are ready to submit your branch for review, after the branch is pushed to GitHub, convert the issue to a pull request:

```text
$ hub pull-request -i <issue number>
```



