# CSCI 3601 Lab #3 - Angular and Spark Lab
[![Build Status](https://travis-ci.org/UMM-CSci-3601/3601-lab3_angular-spark.svg?branch=master)](https://travis-ci.org/UMM-CSci-3601/3601-lab3_angular-spark)

During this lab, you will expand on the ToDo API you created in the previous lab
by building a basic client-side application using Angular 4 which will enable you
to better handle user input, display data returned from the server, and all manner
of other insane things.

Some significant changes to the structure of the project come about in this lab,
so be on the lookout for those. As always, you'll be expected to make good
use of the version control and project management tools available to you:
write good commit messages, test things, document issues, etc.

Your specific tasks for this lab can be found in the [LABTASKS.md][labtasks]
file in this repository.

## Setup

As in the previous lab, you'll be using IntelliJ. Once you've all joined your
group using GitHub classroom, you can clone your repository using IntelliJ:

- When prompted to create a new IntelliJ project, select **yes**.
- Select **import project from existing model** and select **Gradle.**
  - Make sure **Use default Gradle wrapper** is selected.
- Click **Finish.**
- If IDEA asks you if you want to compile JavaScript to TypeScript :fire: DO NOT :fire:
it will break your project.

## Running your project

Now that the structure of the project is different, the way we run the project
is different too.

We have moved or aliased all of the important Gradle tasks to one spot. You can find them
all in `angular-spark-lab / Tasks / application`.

- The familiar **run** Gradle task will still run your SparkJava server.
(which is available at ``localhost:4567``)
- The **build** task (or its' alias **buildExecutable**) will still _build_ the entire project, but not run it.

The major difference here is that the _client_ side of your project is,
effectively, an entirely separate project from your SparkJava server. We've included a full API
for the ToDo's, which you implemented in lab 2, so no need to copy your old project over.

In order to serve up the _client side_ of your project, you'll need to use the
**runClient** Gradle task. This will trigger the various tools in the
client side portion of the project to build and host your client side
application on their own little web-server, available by default at ``localhost:9000``.

## Testing and Continuous Integration

There are now more testing options! You can test the client, or the server or both.

Testing client:
* runAllTests runs both the server tests and the clients tests once. 
* runClientTests runs the client tests once.
* runClientTestsAndWatch runs the client tests every time that the code changes after a save.
* runClientTestsWithCoverage runs the client tests (once?) and deposits code coverage statistics into a new directory within `client` called `coverage`. In there you will find an `index.html`. Right click on `index.html` and select `Open in Browser` with your browser of choice. For Chrome users, you can drag and drop index.html onto chrome and it will open it.  
* runServerTests runs the server tests.

Turn on your repo in [Travis CI][travis], replace the build status image in this README, and push your changes. That will trigger a build with Travis.

## Resources

- [What _is_ Angular 2... why TypeScript?][angular-2]
- [What _is_ webpack...?][whats-webpack]
- [Testing Angular 2 with Karma/Jasmine][angular2-karma-jasmine]

[angular-2]: https://www.infoq.com/articles/Angular2-TypeScript-High-Level-Overview
[angular2-karma-jasmine]: http://twofuckingdevelopers.com/2016/01/testing-angular-2-with-karma-and-jasmine/
[labtasks]: LABTASKS.md
[travis]: https://travis-ci.org/
[whats-webpack]: https://webpack.github.io/docs/what-is-webpack.html
