# Lab 2: Flashcard App - Creating Cards

## Goals

- Understand how to handle navigation within an app
- Understand how to pass data around within the app

Before you start the lab, it may be a good idea to go on the [Skills tab](https://courses.codepath.org/courses/mobile_app_design/unit/4#!skills) and get a quick overview of all the new concepts.  

You may also want revisit some of the [Android Studio Starter Guide Tips](https://courses.codepath.org/courses/mobile_app_design/pages/android/android_studio_intro.md). Awesome tips include how to configure Android Studio to auto-import classes and how to understand why your app is crashing.

If you are running into issues with your emulator or with Android Studio, be sure to check out our [Android Troubleshooting Guide](https://hackmd.io/s/r1KlxitOX)!

## Introduction

Refer to this video for an introduction to the concepts you'll encounter in this lab:

[![Play|700](https://i.imgur.com/IGIzJc9.png)](https://www.youtube.com/watch?v=4gSo_ezf0kc&feature=youtu.be)
- [Lecture Slides](https://speakerdeck.com/marusya82/mad-week-4-lab-2)

## Challenge

Each technical lab has a section of Required and Optional Tasks. Required Tasks MUST be completed as part of your submission, but if you finish those tasks early, feel free to explore the Optional Tasks.

This week we will continue to build our Flashcard app by adding additional features to it. **By the end of this lab your Flashcard app should be able to let users create their own flashcard.** This will only include displaying the user created card, and the app will not be able to save any data yet. In the next lab we will work on implementing saving data!

Once you are done working on your app, follow the guide in the ‘Submission’ section below to submit your work. Your submission MUST include all the Required Tasks but can also include Optional tasks that you had time to work on.

If you get stuck on implementing a certain task, consult the detailed walkthrough linked at the end of each task.

### Required Tasks

#### 1. Start by opening Android Studio and running your app to make sure everything still works as expected.  

Since it may have been a while since you last loaded your project, we want to ensure that everything still works correctly. Run your app and test that the functionalities you implemented from the first lab still work as expected.  

As a reminder, the basic functionality of your app should be that it :
1) displays a question in text form  
2) displays the answer to the question when the question is clicked on  

#### 2. Add a ‘+’ button that takes the user to new ‘Add Card Screen’  

**Concepts / Terminologies introduced** : [Android's Intents](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-intents), [Resources and Drawables](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-resources-and-drawables), [SVG vs PNG](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-svg-vs-png)  

<img src="https://i.imgur.com/dNZIROq.gif" width="200"/>    

- Find and import an icon into your project to be used as the 'Add' button image
- Create a new Activity named `AddCardActivity`
- Set an `onClickListener` for the Add button so that the user is taken to `AddCardActivity` when the button is clicked

Free icons can be found on [iconmonstr.com](https://iconmonstr.com). If you're not sure about how to add Icons into your project, follow the instructions [here](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-adding-icons).

For a more detailed guide on how to add a new Activity and let the user navigate to it, take a look at this [step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-adding-a-new-activity-and-navigating-to-it).  

** The syntax for creating the Intent to launch a new Activity can be tricky and is very error-prone! Ask your group for help debugging if you're not succcessfully able to launch a new activity on a button click.

#### 3. Add a Cancel button to the 'Add Card Screen'  

**Concepts / Terminologies introduced** : [Android's Activity Lifecycle](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-androids-activity-lifecycle)

<img src="https://i.imgur.com/eUtTlue.gif" width="200"/>  
<br></br>

- Find and import an icon into your project to be used as the 'Cancel' button image
- Layouts are automatically created as a `ConstraintLayout`. It would be a good idea to convert `activity_add_card.xml` to use a `RelativeLayout` instead, much like what we did for `activity_main.xml` in the previous lab
- Set an `onClickListener` for the Cancel button so that when the button is clicked, `AddCardActivity` is dismissed and we see `MainActivity` again  

For a more detailed guide on how to dismiss an Activity, take a look at this [step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-dismissing-an-activity).

** Which Activity do you need to add the logic for dismissing the Activity? Make sure you're adding the code at the right place. Ask your group members if you're not sure where to put the code.

#### 4. Add two fields to the 'Add Card Screen' that will allow the user to enter the Question and the Answer  

**Concepts / Terminologies introduced** :  [EditText View](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-edittext-view)

<img src="https://i.imgur.com/Q76WuwL.gif" width="200"/>  

- Add an `EditText` view to the `AddCardActivity` for the question input field
- Add a 'hint' for the `EditText` so that users can know what to type in the field
- Add another `EditText` view with a 'hint' for the Answer input

For more information about `EditText` views and how to customize them, check out this [step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-implementing-edittext-views).  

#### 5. Add a Save button that will dismiss 'Add Card Screen' and return to the Main Activity where the user can see the card they just created  

<img src="https://i.imgur.com/jyXPnBc.gif" width="200"/>   

- Find and import an icon into your project to be used as the 'Save' button image
- Add an `onClickListener` for the Save button so that when it's clicked:
    1) The inputs of the two `EditText` fields are retrieved and put into an `Intent` to be passed back  
    2) `AddCardActivity` is dismissed  
    3) User can see the newly created Question and Answer card in `MainActivity` (this will require taking the data passed back as part of the `Intent`, and re-populating the answer and question TextViews with the new data)  

For a more detailed guide on passing around data between Activities, take a look at this [step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-passing-data-between-activities).  

If you're interested in a more general understanding of how Intents work and how passing data around works, check out this [CodePath Intents Guide](https://guides.codepath.org/android/Using-Intents-to-Create-Flows)  

You may notice that after adding this feature the app now crashes when you click the 'Cancel' button on AddCardActivity. Check out the guide for [debugging general crash errors](https://courses.codepath.org/courses/mobile_app_design/pages/android/android_studio_intro.md#heading-looking-for-crash-errors). If you're still confused on how to fix your crash, here's a [detailed walkthrough on how to fix this specific crash](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-fixing-crash-when-cancel-button-is-clicked-on-addcardactivity)

** This will be the most challenging feature of our whole app so far, and there's a lot that can go wrong in between passing data around Activities, so ask your group mates for help if things don't end up working.

#### 6. Push your code to GitHub!  

After finishing all the Required Tasks, it's time to Push your code to GitHub and go through the submission process to submit your work for the day!  

If you have extra time, check out some of the Optional Tasks below that go deeper into some of the concepts we touched on today.  

As a reminder, instructions for working with GitHub can be found [here](https://courses.codepath.org/courses/mobile_app_design/pages/android/github_how_to.md).  

## Submitting Your Lab Project

Once you have finished all the required tasks and pushed your code to GitHub you'll need to submit your project. If you decide to take on some of the optional feature challenges
1. Create a README in your GitHub repository and paste in the contents of this **[Lab 2 README Template](https://courses.codepath.org/snippets/mobile_app_design/readme_templates_android/02_lab_2_readme.md?raw=true)**
1. In the README, mark off all the features you implemented, using the following syntax`-[x]`
1. Record a GIF walkthrough of your app that showcases the features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.

  :::info
  Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/e07c4196bc7bda432a1bc1f78c295cc8)** to see what a completed README should look like.
  :::

### Optional Tasks

#### 1. Add an ‘Edit’ button on the Main Activity that will let users ‘Edit’ an existing card

<img src="https://i.imgur.com/ikHO0e2.gif" width="200"/>   

- Find and import an icon into your project to be used as the 'Edit' button image
- Create an `onClickListener` for the Edit button that will:  
    1) grab the currently displayed Question and Answer strings  
    2) pass the two strings to `AddCardActivity` so that they can be displayed in the two `EditText` views

For a more detailed guide on passing data while launching an activity, [check out this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-getting-data-when-an-activity-is-created)

#### 2. Show an error message to the user if they didn't enter the question or answer
**Concepts / Terminologies introduced** : [Toast Messages](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-toasts)

<img src="https://i.imgur.com/Yy5GACP.gif" width="200"/>   

- Add in logic so that when the 'Save' button is clicked, if either of the `EditText` views aren't populated, we show an error message in a `Toast`

For more instructions on how to display toast messages, check out [this CodePath guide](https://guides.codepath.org/android/Displaying-Toasts)

** Where should you put the logic to show the Toast message? Try to think about at what point you would want to show the user this message. Discuss with your group if you're not sure where to add the code to show the toast.

#### 3. Display a Snackbar notification for when the new card is created successfully
**Concepts / Terminologies introduced** : [SnackBar Messages](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_2_glossary.md#heading-snackbar)

<img src="https://i.imgur.com/LJDqXeV.gif" width="200"/>    

- In `MainActivity`, show a `SnackBar` message when we get result back from `AddCardActivity`  

For more instructions on how to display Snackbar notifications, check out [this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab2_walkthrough.md#heading-displaying-a-snackbar-message)

#### 4. Allow the user to add Multiple Choice answers when creating the card
This step requires that you've completed some Optional steps 4 and 5 from the [previous lab](https://courses.codepath.org/courses/mobile_app_design/unit/2#!labs). Head on over to implement the two Optional steps before implementing this feature.

<img src="https://i.imgur.com/gJjCqKK.png" width="200"/>        <img src="https://i.imgur.com/60Gmd1z.gif" width="200"/>   
This will require some extra data to be passed from `AddCardActivity` to `MainActivity` . For a refresher on passing data back to the original activity, check out [this CodePath guide](https://guides.codepath.org/android/Using-Intents-to-Create-Flows#returning-data-result-to-parent-activity)

#### 5. Further customize and style your app!
An app can always be made better with better UI styling. Feel free to explore different ways that you can improve the UI of your app.  
- There are many different ways to style your EditText views, and you can read more about it all [here](https://guides.codepath.org/android/Working-with-the-EditText).
- You can also add backgrounds for your views like what we did in the optional tasks for the first lab. For a refresher on styling views, revisit the lab 1 guide walkthrough step [here](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab1_walkthrough.md#heading-advanced-view-styling)  

### Re-submitting Your Lab Project After Completing Optional Features
Anytime you complete more optional features for your app, you'll need to update your submission and re-submit.
1. Update your README by marking off any additional optional features you implemented, using the following syntax`-[x]`
1. Record a new GIF walkthrough that showcases the new features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
1. Submit your app using the same **Submit** button found at the top of this lab page.

:::info
Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/e07c4196bc7bda432a1bc1f78c295cc8)** to see what a completed README should look like.
:::
