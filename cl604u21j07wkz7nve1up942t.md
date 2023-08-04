---
title: "Automating Workflows with GitHub Actions & CI/CD Pipeline"
seoTitle: "Beginner friendly explanation of how GitHub Actions operate and CI/CD"
seoDescription: "GitHub Actions is a platform to automate software developer workflows which means that using GitHub Actions we can create some tasks that occur automat"
datePublished: Mon Jul 25 2022 02:31:00 GMT+0000 (Coordinated Universal Time)
cuid: cl604u21j07wkz7nve1up942t
slug: automating-workflows-with-github-actions-cicd-pipeline
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1658014063594/56ZqNV8f-.avif
tags: github, developer, beginners, github-actions-1, blogswithcc

---

### *What is GitHub?*

It is a platform for many open-source projects. Developers or companies can make their projects publically available on GitHub as open-source projects so that the community can use or contribute to them.

### *What is GitHub Actions?*

It is a platform to automate software developer workflows which means that using GitHub Actions we can create some tasks that occur automatically when a certain event happens.

For example:- When you contribute to an open-source project, it is visible that some checks are performed. These checks happen automatically because it will be really very hard to perform checks manually on each and every contribution. So this is where GitHub Actions comes into place.

### *Is Github Actions a CI/CD platform?*

No, CI/CD is just one of the many workflows that we automate using GitHub Actions.

### *What are those workflows?*

![Screenshot (29).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658011621606/lIzQVc-S3.png align="left")

There are different types of workflows like when a team or individual developers who manage these projects need to manage pull requests, new issues, merge pull requests, assign a person to an issue, check whether the issue is fixed or not, check if the issue fixed is not creating an issue at someplace else in the project if a fixed issue creates another issue then to make that issue public. So these are just some of the workflows that a maintainer has to perform.

So just imagine in a bigger project there will be a lot more features, a lot more tasks, a lot more contributors, and a lot more tasks that will only lead to chaos.

![chaos.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1657561938143/ihULWfvA5.gif align="center")

So this is where Github Action comes into play and can help you automate as many things as possible. Some automatic actions can be configured by the user that are executed whenever some changes happen in or to your repository. These changes are called **GitHub Events**.

![GitHub Actions.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657583107657/yS1UWLm5C.png align="center")

### *How do GitHub Actions automate these workflows?*

To automate specific workflows the user listens to events and based on that event the user assigns a specific workflow that executes automatically.

### *Advantages of GitHub Actions:-*

If the user hosts the project already on GitHub then instead of a third-party tool the user can use GitHub Actions. GitHub Actions makes setting up the pipeline very easy. No need for you to hire a DevOps engineer who sets up or maintains the CI/CD pipeline because it's made in such a way that developers can also use it.

### *Why is setting up and managing of the CI/CD pipeline in GitHub Actions so easy?*

Its integration with different tools. No matter what different combinations of application or tools we require, we don't need to install or configure these applications or tools the CI/CD pipeline provides us with all these environments. We can also set the version of the application that we want. The deployment can also be done easily by just connecting to the targeting environment and deploying the application there.

### \*\*CI/CD DEMO \*\*

This action tab is integrated into your project beforehand. Click on "Action".

![Untitled design.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657911257910/Caz1jOvJ6.png align="left")

After clicking on the Actions tab you'll see a list of workflow templates for different categories of operation. You can also make your own workflow with different combinations and adjust it.

![Screenshot (16).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657911785929/vKoVsPAWh.png align="left")

![Screenshot (19).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657911796119/r9VmgFsDr.png align="left")

Syntax of the workflow file

```go
name:                             

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

permissions:
  contents: read

jobs:
  build:

    runs-on: ubuntu-latest

    steps:

    - uses: actions/checkout@v3
    - name: Set up JDK 11
      uses: actions/setup-java@v3
      with:
        java-version: '11'
        distribution: 'temurin'
    - name: Build with Gradle
      uses: gradle/gradle-build-action@67421db6bd0bf253fb4bd25b31ebb98943c375e1
      with:
        arguments: build
```

### The above code is explained in a detailed format below:-

The name of the workflow describes what the workflow is doing.

![Screenshot (24).jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1657936312162/hkmRqcnEh.jpg align="left")

On lists all the events that will trigger this workflow. So in this case, if someone pushes to the master branch or every time a pull request gets created with the master branch as a target the workflows mentioned inside ***jobs*** get executed.

![Screenshot.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1657936540164/CS0654Wd-.jpg align="left")

Jobs contain different workflows that are executed once any event inside \*\*\*on \*\*\* is triggered. There can be multiple jobs. So Job groups a set of actions that will be executed.

![Screenshot (25).jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1657936760272/nIse1um7n.jpg align="left")

Whenever we want to build an application or run a test we need to check out the repository or the code first. So "**actions/**" path in GitHub is where predefined actions are hosted. This is present so that the user does not have to write it. The @v3 after checkout is the version of checkout.

So the "uses" attribute helps us to use predefined actions either in GitHub Actions repository or if any other community has created one.

The "run" attribute helps us to run a command line command.

![Screenshot (27).jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1658002953366/h7cjrGqli.jpg align="left")

### **The details and list of all the events that can be used are found in the below link:-**

https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows

![Screenshot (21).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657913268806/0r8aftzaq.png align="left")

### *Where does this code run?*

Workflows and GitHub Actions get executed on GitHub servers and are managed by them. Every time you create a new workflow with a set of jobs for every single job a fresh new GitHub server will be prepared. So one job runs on one single server at a time. If multiple jobs exist in a workflow they run in parallel. These servers are called runners. Whenever an event occurs it goes to the runner.

### **Thank you all for giving your valuable time for reading.**

### **Resources:-**

[**TechWorld with Nana's Youtube tutorials.**](https://www.youtube.com/watch?v=R8_veQiYBjI&t=1s)

[**Kunal Kushwaha's youtube tutorials.**](https://www.youtube.com/watch?v=62N8UiWUdQo&t=207s)

[**GitHub Actions Documentation.**](https://docs.github.com/en/actions)

### ***Any feedback or remarks will be highly appreciated.***