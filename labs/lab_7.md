# Lab 4: Flashcard App - Animations and Styling

## Goals

- Understand how and when to implement different types animations within your app
- Style your app!

Before you start the lab, it may be a good idea to go on the [Skills tab](https://courses.codepath.org/courses/mobile_app_design/unit/8#!skills) and get a quick overview of all the new concepts.  

**A list of common bugs you may run into during the lab and how to solve the bugs are detailed [here](https://hackmd.io/s/ry_mZvLRX).** It may be helpful to consult this guide before reaching out for help.

If you are running into general Android/debugging issues, check out our guide on [how to solve technical issues when building Android apps](https://hackmd.io/s/r1bhe4La7). **If you find that you're stuck on a step for more than an hour or so, ping the @mad-android-support group so one of the TAs can help you debug the issue.**

## Introduction

Refer to this video for an introduction on the concepts you'll encounter in this lab:

[![Play|700](https://i.imgur.com/MjodaGp.png)](https://www.youtube.com/watch?v=TfqeqDXU7EQ&feature=youtu.be)
- [Slides](https://speakerdeck.com/calren/mobile-app-design-lab-8-android)

## Challenge

This week we will continue to build our Flashcard app. **By the end of this lab your Flashcard app should be spruced up with custom animations and styles!** The goal of this lab is to build out your app so that you'd be proud to show it off to your friends and family.

If you get stuck on implementing a certain task, consult the detailed walkthrough linked at the end of each task.

### Required Tasks

#### 1. Start by opening Android Studio and running your app to make sure everything still works as expected.  

Since it may have been a while since you last loaded your project, we want to ensure that everything still works correctly. Run your app and test that the functionalities you implemented from the first lab still work as expected.  

At this point, your app should be able to:
1) Allow users to create cards
2) Allow users to browse through multiple cards

#### 2. Add a launcher icon for your app!  

<img src="https://i.imgur.com/w0LchHC.gif" width="200" />  

Up until now, we have been using the default launcher icon for our app (the green Android icon). This isn't very exciting, but luckily it's very easy to personalize the icon for your app!  

First, find an icon that you want to represent your app (if you recall, [iconmonstr.com](https://iconmonstr.com/) is a great place for icons. google image searching for something like 'flashcard icon' is also a great way to find icons). Then, go to File > New > Image Asset. Select "Launcher Icons" as the Icon Type, and then load your chosen icon. Now, when you run your app again, you should see the icon you just added in the list of apps installed on the phone!  

For more detailed instructions on how to add this icon, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-adding-a-launcher-icon)

#### 3. Add a transition animation when the app goes from MainActivity to AddCardActivity  

**Concepts / Terminologies introduced** : [Activity Transition](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_4_glossary.md#heading-activity-transitions), [View Animations](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_4_glossary.md#heading-view-properties---property-animators)  

<img src="https://i.imgur.com/3aBXoMp.gif" width="200" />  

When the user presses the "+" button to navigate to AddCardActivity, they should see an appropriate transition animation. The example shows MainActivity going out to the left and AddCardActivity coming in from the right.

For more details on how to implement activity transitions, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-implementing-activity-transition-animation).   

#### 4. Add an animation for when the answer is revealed.  

<img src="https://i.imgur.com/FXdd805.gif" width="200" />

For this animation, we reveal the answer with a 'circular' reveal animation where the center is revealed first followed slowly by the edges of the view.

For more details on how to implement this animation, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-add-a-reveal-animation-for-when-the-answer-is-revealed).

#### 5. Add a sliding animation for when the user advances to the next card.  

**Concepts / Terminologies introduced** : [Animation Listener](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_4_glossary.md#heading-animationlistener)  

<img src="https://i.imgur.com/BoDu5Xs.gif" width="200" />  

It'd be neat if we simulated cards going out and coming in when the user hits the 'next' button to bring in a new card. For this animation we can actually reuse the animations we wrote for transitioning from MainActivity to AddCardActivity!  

For more details on how to implement these animations, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-add-an-animation-for-when-the-next-card-is-shown).

#### 6. Add some last touches!  

Take an audit of your app and think about what else you can do to make it look better! Some easy wins are:
- Adding margins for text and buttons
    - It generally doesn't look good if content is too close to the edges. You can easily fix this by adding margins for your views
- Adding colors (for your text or background) can make a big difference! Using a good set of colors is also crucial. If you need some ideas for color themes, check out [https://www.color-hex.com/color-palettes/](https://www.color-hex.com/color-palettes/)
- Having properly sized icons
    - are the icons in your app properly centered and not cut off or inappropriately sized so that it looks blurry?

**Congrats on finishing your first Android app!!!**

## Submitting Your Lab Project
 Once you have finished all the required tasks and pushed your code to GitHub you'll need to submit your project. If you decide to take on some of the optional feature challenges
1. Create a README in your GitHub repository and paste in the contents of this **[Lab 4 README Template](https://courses.codepath.org/snippets/mobile_app_design/readme_templates_android/04_lab_4_readme.md?raw=true)**
1. In the README, mark off all the features you implemented, using the following syntax`-[x]`
1. Record a GIF walkthrough of your app that showcases the features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
   :::info
  Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/8c11b1986fec63a684aa2797739acd0c)** to see what a completed README should look like.
  :::

### Optional Tasks

#### 1. Styling views  

<img src="https://i.imgur.com/T92I0EY.png" width="200" />   

If you didn't have the chance to style your views in the first lab, this is a great time to go back and do that. You can follow the guide from the previous lab on styling views [here](
https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab1_walkthrough.md#heading-advanced-view-styling).  

Styling your views to give them a border and rounded corners can make a big difference in how your app looks!

#### 2. Add a countdown timer for each question

<img src="https://i.imgur.com/m76aEx3.gif" width="200" />   

If users wanted to review cards in a 'fast' mode, you can add a countdown timer to indicate how long the user has left to answer the question. The timer would reset every time a new card comes in.

For more details on how to implement this, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-adding-a-countdown-timer).

#### 3. (Advanced Optional) Replace the answer 'reveal' animation with a 'card flip' animation

<img src="https://i.imgur.com/Wlecqey.gif" width="200" />   

For this animation, we will replace the original 'circular reveal' animation. Instead, we want the card to simulate being 'flipped' when the user taps on it.  

For more details on how to implement this animation, [follow this step in the guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-adding-a-card-flip-animation).

#### 4. Add a celebration animation if the user answers the question correctly.

This will require you to have implemented some of the optionals from the previous labs regarding multiple choice. So if you haven't had the chance to implement multiple choice in your app yet, head on over to the previous labs to check that out!  

<img src="https://i.imgur.com/m7A7ELf.gif" width="200" />   

The goal of this feature is to simulate some confetti being thrown when the correct answer is chosen. This will require integrating an animation library.

Check out the [detailed guide for this step here](https://courses.codepath.org/courses/mobile_app_design/pages/android/walkthroughs/lab4_walkthrough.md#heading-adding-a-confetti-animation).

### Re-submitting Your Lab Project After Completing Optional Features
 Anytime you complete more optional features for your app, you'll need to update your submission and re-submit.
1. Update your README by marking off any additional optional features you implemented, using the following syntax`-[x]`
1. Record a new GIF walkthrough that showcases the new features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
1. Submit your app using the same **Submit** button found at the top of this lab page.
 :::info
Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/8c11b1986fec63a684aa2797739acd0c)** to see what a completed README should look like.
:::
