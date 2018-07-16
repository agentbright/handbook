# New Pull Requests

When we push our code and convert an issue to a pull request, a number of automated things take place:

## Heroku staging app deployment

Heroku will automatically deploy a new staging app, located at **agent-bright-staging-pr-&lt;issue number&gt;.herokuapp.com**. eg. https://agent-bright-staging-pr-3256.herokuapp.com.

{% hint style="info" %}
If you get a message saying there has been a problem with deployment, go to [heroku.com](https://www.heroku.com) and check the app pipeline. From there you can see the deploy log and retry, or delete/recreate the app instance.
{% endhint %}

## CircleCI

The test suite is automatically run on each push by CircleCI.

CircleCI has three stages: build, tests, and upload-coverage.

## CodeClimate

CodeClimate will review the code for styling issues, code smells and security risks.

CodeClimate also will compare test coverage. All new code must have more than 90% coverage to pass.

{% hint style="warning" %}
If you are getting failing checks for code coverage in files that you have not changed in your pull request, try rebasing your branch to bring it up to date with master.
{% endhint %}



