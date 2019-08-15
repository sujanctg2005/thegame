## Project 4: Workflow, Automation via Probot 

## Prompt Description

### Intro

In this prompt, we are going to learn how to build a GitHub App on top of the game repo. In particular we will learn how to:

1) Register a new app with GitHub
2) Get started using Probot to help us focus on the interesting parts
3) Learn about the GitHub Event system, and how to receive and handle events
4) Learn about how to make calls to the GitHub API to accomplish tasks

We are going to begin by building an app that posts a greeting in response to a new issue being opened up. Then we will modify this app to transform it into a useful tool to triage issues using a little machine learning.

Probot docs, in case we ever get lost: https://probot.github.io/docs/

### Part 1: Getting Started

#### Step 1: Create and register our app

- Remix on Glitch: https://bit.ly/remix-probot
-  Provides instructions in-app, how nice!
**Note**: Glitch has tools in the bottom left corner where you can see the log output — you can use this to debug your app if you get stuck

![image](https://user-images.githubusercontent.com/410195/54273049-39b78f80-4542-11e9-922e-9b3bae3ce8e3.png)

- Create a sandbox repo to play in

- Follow instructions in Probot readme

- Don't forget to upload an avatar, or it uses yours and it might be confusing.

#### Step 2: Finish configuring the app

- Set up `ENV` variables in your Glitch Remix, following the instructions

#### Step 3: Test our app

- Create a new issue!

- Did the app respond? Yay! Otherwise, let's troubleshoot!

### Part 2: Adding a twist on our App

Now, let's change our code up. Instead of replying to new issues, let's triage them. The goal is to build an app that will look at incoming issues, and classify them as "bug reports", "feature requests", or "questions" automatically for us! Let's use some fun NLP for that.

What we will need to do is this:

1) Grab the title of the issue
2) Pass the title to a text classification API—recast.ai
3) Determine whether the title is a command, a request, or a question
4) Add labels to the issue depending on on how we classified the text

- Hit https://recast.ai/ and sign in with GH

- Create a new project on the website. Walk through the demo interface to show what the API does for us. Examine the sample JSON responses

- Get the token from the project. This can be tricky to find.

- Add token to the .env file under `RECASTAI_TOKEN`

> Add recastai module manually in the package.json in Glitch Remix if needed: "recastai": "^3.7.0"
> Don't confuse it with the "recast" module!

- Now, we need to make some API calls: Walk through each step at
https://git.io/fbpdc


- Finally, test it! Open some sample issues in the sandbox repo, and watch how the app tags each of them. It's not perfect, but it should serve as an inspiration to go further!

> enhancement:
> Add support for Windows Phone

> bug:
> This thing is broken

> question:
> Can you help me?

### Part 3: You're Finished! 

You have an app! Congratulations. You have begun to automate your workflows. We hope you're feeling inspired! Keep moving with it, and see how you can extend it to do other interesting things!

## Pre-requisites

- GitHub, especially issues
- Writing code with JavaScript (beginner-level)

## Learning Outcomes

- [ ] GitHub Apps
- [ ] GitHub Events
- [ ] Workflow Automation in GitHub

## Technologies used

- JS
- GitHub Apps
- Probot
