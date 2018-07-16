---
description: How we use overcommit to run checks on our code locally
---

# Overcommit

## Pre-commit checks

Overcommit will make the following pre-commit checks:

* Check Gemfile dependencies
* Check for local paths in Gemfile
* Check for merge conflicts
* Check that the database schema is up to date
* Check for trailing whitespace
* Check for any "FIXME" comments
* Analyze YAML syntax 
* Analyze Javascript using **ESlint**
* Analyze SCSS using **scss-lint**
* Analyze Ruby using **rubocop**

When you commit your changes, overcommit will run the pre-commit hooks:

```text
$ git commit
Running pre-commit hooks
Check YAML syntax........................................[YamlSyntax] OK
Check for local paths in Gemfile................[LocalPathsInGemfile] OK
Check if database schema is up to date..........[RailsSchemaUpToDate] OK
Check for trailing whitespace....................[TrailingWhitespace] OK
Check for "token" strings.....................................[FixMe] OK
Check Gemfile dependencies..............................[BundleCheck] OK
Analyze with scss-lint.....................................[ScssLint] OK
Analyze with ESlint..........................................[ESLint] OK
Analyze with RuboCop........................................[RuboCop] OK

✓ All pre-commit hooks passed
```

## Commit message checks

Once you have entered your commit message, overcommit will run commit-msg hooks:

```text
Running commit-msg hooks
Check commit message matches expected pattern.........[MessageFormat] OK
Run CapitalizedSubjectMessage.............[CapitalizedSubjectMessage] OK
Check text width..........................................[TextWidth] OK
Check subject line................................[SingleLineSubject] OK
Check for trailing periods in subject................[TrailingPeriod] OK

✓ All commit-msg hooks passed
```

## Run overcommit manually

To run overcommit without actually committing anything:

```text
$ overcommit --run
```

{% hint style="warning" %}
This will run the checks across the entire repository, not just the files you've made changes to.
{% endhint %}

## Overriding overcommit

There will be times when you need to make a commit despite an overcommit failure. You might be fixing code that has an issue that is out of scope. Or you might want to commit work-in-progress changes.

You can skip overcommit by running:

```text
$ git commit --no-verify
```

