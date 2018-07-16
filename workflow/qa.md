# QA

## Overview

When we have finished an issue and all of our tests and checks are coming up green, the pull request is ready to be reviewed.

For a pull request to be merged, it has to go through two QA checks: **code review** and **testing review**.

## Testing review

When the issue is ready to be tested:

1. Move it to the **QA** pipeline
2. Add the label `Ready for: Review` or `Ready for: Testing`
3. Add `annieogrady` as an assignee
4. Add a comment on the issue, addressing the testers, saying that the issue is ready for review. Include any additional information that you may want to communicate.

```text
@annieogrady @heyogrady ready for review
```

The test reviewer will visit the Heroku staging app deployment, verify that the acceptance criteria has been met, and that there are no additional changes.

## Code review

Assign @heyogrady as a reviewer.

## Rework

If either the code reviewer or test reviewer has any questions, comments or requested changes, they will leave comments with those changes, and then apply the label `Ready for: Rework`.

## Merging

When the test reviewer and code reviewer have both approved the issue, then it is ready to be merged into the `master` branch.

If a new commit is pushed to the `master` branch, CircleCI will run the test suite, and if it passes, Heroku will deploy the changes to our staging site at: [http://www.agentbright.us](http://www.agentbright.us)

