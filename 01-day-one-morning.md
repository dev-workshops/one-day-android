---
title: Command Line and Why you need it
duration: "~3:00"
creator:
    name:
    city: Dar es Salaam, Tanzania
---

### LEARNING OBJECTIVES
*After this workshop, students will be able to*
- Know the agenda
- Have all pre-requisites installed
- Understand why command line is powerful
- Navigate to a directory via the terminal
- Understand the power of Github
- Download a git repository

### STUDENT PRE-WORK
*Before this lesson, you should already*
- Have Java installed
- Have Android Studio installed
- Have the proper SDK installed
- Have [git](https://git-scm.com/) installed

### INSTRUCTOR PREP
*Before this lesson, instructors will need to*
- Have the needed installs ready on 5+ USB Drives
- Figure out a one sentence introduction for yourself

> This lesson plan goes from Slide x to Slide y

## Opening (10 minutes)

Who hasn't yet installed the needed dependancies?

> If necessary: Get a classroom assistant to go around handing out USB sticks. Give basic procedural guidance for staring download.

> Note: Any student who comes in late should be asked immediately if he has the software installed and be sat next to someone with a USB. When student 1 completes, they are responsible for helping start the download for student 2.

#### Who's here?
- Introduce self
- Ask students to introduce themselves and provide a one-sentence background description

> Ask for experience. Require people to pair up: A person with no experience should sit next to and work with someone with more experience. Also important: encourage the one with less experience to type, and the one with more experience to drive.

#### Day Agenda:
What we'll learn:
- What's in an Android app
- Version control and why it's important
- How to use jUnit for rapid testing

What we'll be trying to build:
- A basic android app with a button you can click on


Before lunch agenda:
- Learn about the basic components of an android app
- Learn about the command line
- Learn about Github

After Lunch agenda:
- Use jUnit to:
  - create variables and methods
- Learn how to manipulate text in android
- Create a basic ui
- Add a click listener


Expectations:
- It's going to hurt your brain
- Ask questions
- Google & Stack Overflow are your friends
- We will hit errors. That's part of the "fun"

Your Takeaways:
- I hope to give you increased confidence in your ability to continue learning on your own

> Check: How is software installation going? Does anyone still need help getting software installed?

## Introduction: Parts of an Android app (20 mins)

#### Parts of an app

- Layout xml (like HTML) - Define the UI for your app
- Java code (like Javascript) - The java does the "work" of the app
- AndroidManifest.xml - configuration file
- build.gradle - dependancies file

> Instructor Note: Show where each of the files can be found in the Android project that will be used during the workshop.

#### Other words to know:
- Activity
- Intent
- Fragment, Service, BroadcastReceiver, ContentProvider, etc...
- ACTIVITY == SCREEN
- INTENT == MESSAGE

Check: Identify the 4 basic parts of an Android app and their purpose.


## Demo: The Command Line and Java (20 mins)

Be sure to leverage the web:
- Google, StackOverflow, GitHub
- There is a "right" way to Google
- Be efficient: Use the keyboard, terminal (command line) as much as humanly possible

Developers should always:
- Leverage the web
- Google, StackOverflow, GitHub
- Google the "right way"
- Be efficient
- Use the keyboard, terminal (command line) as much as humanly possible

The command line is the heart of your OS. You can do anything you could do in finder in the command line but faster! Oh and by the way, "Directory" = "Folder".

> Instructor Note: Students should open their terminals or Git Bash shells if on PC.  Also, open your finder and encourage students to do the same to see how updates made in the terminal affect our file and folder structure.  You should be driving home the fact that the terminal is doing the same thing as a finder but with text commands instead of clicks.

Let's try the following commands together:
- pwd - List the contents of the directory
- ls/dir(windows) - List all files and folders in current directory
- cd - Change directories
- mkdir - Create a new folder
- rmdir - Remove an empty folder
- touch - Create an empty file
- rm - remove a file
- cp - Copy a file
- atom - Open the directory you're in with a text editor
- cd .. - Move up one directory
We can chain folders into the ".." parameter...

> Instructor Note: Demonstrate relative vs. absolute paths

Check: Were those commands able to work and are you seeing what you see on my screen?

## Independent Practice: Command Line (15 mins) *optional*

Keep your finder window opened - so you can check your work - and from your desktop:

- Create a directory called "days_of_week"
- Create two more directories within the "days_of_week" directory: "weekend" and "weekdays"
- Within the "weekend" directory, create two files: saturday.html and sunday.html
- Within the "weekdays" directory, create five files: monday.html, tuesday.html, etc
- Work with a partner!

Check: Were you able to have a top folder with two subfolders and the correct days of the week within?

## Break (10 mins)

## Introduction: Git/GitHub (30 mins)

#### What is Git?

- Think Microsoft Office in 1999 - but with "version history" from Google Docs
- Code manager or "version control software"
- It's super smart
- The real benefit is when you're working in teams, but let's ignore that for now

Let's try initializing a git repository and committing a version in time:

```
git init
git add .
git commit -m "your message"
git log
```

Check: Were you able to see a commit confirmation after your git commit?

With Git, nothing is lost (if you do it right!)

> Instructor Note: Demonstrate making a small code change in the Android repository, adding/commiting, and then checking out to your first version. Do not have students run checkout with you - just demonstrate.

#### What is GitHub?

- A service that lets you host Git repositories (fancy word for "projects") on the internet
- Allows for easy sharing of code
- There are public sources of code (Reddit) and private sources of code (predict)

Let's all sign up for GitHub, if you haven't already.  

> Instructor Note: Walk through the slides (starting at slide 39) with Git/GitHub visualizations, explaining slowly.  Provide students with a link to the last slide of the GitHub visualization to use as a reference: https://i.imgur.com/07OiOrs.png.

## Guided Practice: Forking and Cloning (20 mins)

I have created a basic android project that we will use for this workshop. First, I will check that I don't have any unsaved changes. Then I'll add/commit those changes...Then I'll push those changes.

#### Your turn
"Fork" my changes, so you have them on GitHub and then clone that repository to your local machine.  You have my project!

Check: Do you have my project on your local machine.

## Demo: Looking at a GitHub project (10 mins)

Let's take a look at the project.
*TODO: Add repo link here*
*TODO: Consider replacing this exercise*

What information can we find about this project history?

> Instructor Note: Show where to find commits, branches, contributors, etc.

## Independent Practice: Find out information from Github (15 mins)

Visit *TODO: Add repo link here* and answer the following questions:

*TODO: Update questions*
- What version are they up to?
- Which user is the second-greatest contributor to this repository?
- How many commits were made on August 12th?
- On the April 12th, 2015 commit:
  - How many files were modified?
  - How many lines were added?
  - How many lines were deleted?
  - What are the names of the files that were modified?

Check: Let's review the answers to these questions.

## Conclusion (10 mins)

- Explain the basic structure of an Android application
- Explain how UI elements and Java logic communicate     
- Describe how to share code using Git/GitHub
