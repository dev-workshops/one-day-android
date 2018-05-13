---
title: Data types, functions, and app UI
duration: "~3:00"
creator:
    name:
    city: Dar es Salaam
---


### LEARNING OBJECTIVES
*After this workshop, students will be able to*
- Describe the use cases of different datatypes;
- Declare and manipulate data stored in a variable
- Create basic functions  
- Create a xml with a user input field  
- Add a click listener to a view  
- Get string data from an input                               


### STUDENT PRE-WORK
*Before this lesson, you should already be able to*
* Create and manipulate files and folders from the command line
* Clone from github

### INSTRUCTOR PREP
*Before this lesson, instructors will need to:*
- Become familiar with the github repository, including all branches

> There is buffer time built into this lesson plan.  The lesson plan goes from slide ?-?

## Opening (10 mins)

Lets recap the morning:

- What part of an Android app handles the logic?
- Gary is a co-worker working on a side-project and asked me to help - what should Gary do and what should I do to make sure I can edit Gary's code on my computer?

## Introduction: Why Java? (15 mins)

Well, for Android, you need it.

Some context:

- Created by James Gosling/Sun in the mid-90s
- Was supposed to be "write once, run anywhere"
- Basically for servers
- Android first serious UI usage
- Object oriented

#### Java Compilation

Java code is just text that is later "compiled" into machine readable code. All languages technically do this at some point.

There are some unique ideas relating to Java:

- (Mostly) Everything is a class/object
- Unlike scripting languages, you can't just "run" a file

## Demo: Data types (30 mins)

>Instructor Note: Be sure to attempt to have students code along with you in some type of interactive Java shell. We do not have one recommended right now. Just creating and manipulating strings and numbers on the fly is helpful for students to see.

Java is all about primitives and objects. Primitives are basic data types and objects are data collections (basically).

An object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.

All programming languages have something like the following: numbers, strings, booleans, collections.

#### Numbers

These include:

- Integers
- 1, 5, 245, -42, 24142341351324
- byte, short, int, long
- Floats
- 1.1, 2.000043, -0.5522001
- float, double

#### Strings
- any kind of text
- donated by double quotes

#### Booleans
Think of these as a yes/no kind of value.

#### Variables

Variables are simply a place to store data. The type of data is declared before the variable name (Java has stong typing). Variable names, by convention, start lower case, with capitals for new words (Camel case).

<img src="https://i.imgur.com/D7ud1Bi.png">

...and you can join strings by concatenating variables!

<img src="https://i.imgur.com/f3F7zPC.png">

#### Some methods we'll be writing

`System.out.println(wholeString);` writes a string out to the terminal.

`System.in` reads lines from the terminal.  Think of this as accepting user input.

## Guided Practice: Writing Methods (25 mins)

A method is a list of instructions.  When creating methods, you'll see some other words floating around. Visibility is only important once you get into classes, and if you see synchronized, you're probably in the wrong place.

Note that all methods are part of a class (but don't worry about that yet).

All methods have:
- A return type
- A name
- (optional) Parameters
- The code body

To call a method, use the name, pass params, and profit.

#### Code along (JUnit)
For the following few exercises we will be writing methods and asserting that the
results are what we expect by using jUnit. Automated testing is a powerful way to
ensure that the code we write works the way we expect it too.

Do this with me:

- Open the repo that we cloned earlier and create a java file called YouSaidTest.java
- Write a method that takes a string input that prints it out with "You said: ", and the string param
- Call the method and assert that your answer was correct in a jUnit Test

You should have gotten:

```java
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class YouSaidTest {

    public String youSaid(String userInput) {
        return "You said: "+userInput;
    }

    @Test
    public void youSaid_isCorrect() {
        String result = youSaid("blue");
        assertEquals("You said: blue", result);
    }
}
```

## Independent Practice: Refactor the code (15 mins)

#### Git branches
Have you ever made a copy of something, because you didn't want to lose the original?
Git branches are a useful tool to add to your toolkit. They can be used for building a feature, or fixing a bug in an isolated sandbox, meaning the code that you write won't effect other people, and can be easily merged or deleted, as necessary.

The Android project we are using for this workshop has a few branches. Let's look at them now.

```
git branch                            # shows a list of branches
git checkout <branch-name>            # checks out a branch
git checkout -b <branch-name>         # creates a new branch
```

You can switch to a different branch with the `git checkout <branch-name>` command.

Everyone please checkout branch `user-input`. Notice that this branch contains another test file `MathTest`, and that it is broken. Your task: Fix the test!

Create a function that takes as parameters two numbers, and returns the product of those numbers. Run the android unit test and assert that your new function works as expected.

> Instructor Note: Go slowly when walking through git branching.

## Break (5 mins)


## Demo: Android Input Forms (20 mins)

We are now going to start really building an android application.

Please do the following:
* Open up `BasicActivity`.
* Notice the line `setContentView(R.layout.activity_basic)`
  *check* What do you think this line does?
* Open up `R.layout.activity_basic`
* Add the following, explaining each part:

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <android.support.design.widget.TextInputLayout
        android:id="@+id/tilYouSay"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="@string/say_it_hint">

        <android.support.design.widget.TextInputEditText
            android:id="@+id/etYouSay"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
    </android.support.design.widget.TextInputLayout>

    <Button
        android:id="@+id/btnSayIt"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/btn_say_it"
        app:layout_constraintTop_toBottomOf="@+id/tilYouSay" />

</android.support.constraint.ConstraintLayout>
```

* Hardcode a string, and note the lint error. Fix it.
* Reasons you should use string resources, rather than hardcoded strings include:
  - translation
  - easy to update
* Show the design tab
* Ask students, what they think would happen if they ran it now. Would the button be clickable? What would it take to make it interactive?
* In `BasicActivity.java`:
  * grab the input element by it's id.
  * grab the button by it's id.
  * copy over the get user input method from the jUnit test. Make it public static, so the test doesn't break.
  * add a click listener to the button that gets the input, calls the method, and makes a toast with the result
* Run it.

> Instructor Note: As you code, talk about the typical way that a android file is setup, with the variables on top, followed by the lifecycle methods, followed by the private methods.

> Bonus (if time): Add a verify method and show an error if user input is empty

## Independent Practice: User Input Forms (20 mins)

> Instructor Note: Push the code. Ask students to pull. Ensure they all have the updated code.

Now your turn.

Add another two input boxes to this activity, and another button, labeled "Multiply". Hook up the method that you wrote in `MathTest.java`. Toast the result.

> TODO: Find bonus activities. Setup branches with fragments etc. for students to look at.

## Conclusion (10 mins)

Let's review the following:
- Basic Android bits
- Command line
- Git
- Basic Java and types
- Methods
- Android xml & click listeners
