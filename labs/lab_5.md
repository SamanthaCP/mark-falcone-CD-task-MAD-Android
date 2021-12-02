# Lab 3: Flashcard App - Saving Cards

## Goals

- Understand how to save data within an app
- Understand how to retrieve saved data within an app

Before you start the lab, it may be a good idea to go on the [Skills tab](https://courses.codepath.org/courses/mobile_app_design/unit/5#!skills) and get a quick overview of all the new concepts.  

If you are running into build errors, emulator errors or want a refresher on Android Studio, you can revisit the [Android Studio Starter Guide Tips](https://courses.codepath.org/courses/mobile_app_design/pages/android/android_studio_intro.md) or the [Android Troubleshooting Guide](https://hackmd.io/s/r1KlxitOX)

## Introduction

Refer to this video for an introduction to the concepts you'll encounter in this lab:

[![Play|700](https://i.imgur.com/qMYWgS2.png)](https://www.youtube.com/watch?v=v1DMLdIh4Xc)
- [Lab 3 Lecture Slides](https://speakerdeck.com/calren/mobile-app-design-lab-6-android)

## Troubleshooting

As you are working through the lab it is inevitable that you'll run into some issues. Check out a list of common issues and how to resolve them [here](/pages/android/troubleshooting/hints_5.md). If you have been stuck on an issue for more than an hour or two, please be sure to reach out in order to get unblocked.

## Challenge

This week we will continue to build our Flashcard app. **By the end of this lab your Flashcard app should be able save multiple user created cards so that users can revisit the app to review their cards.**

This is what the flashcard app will look like at the end of this lab:

| First Checkpoint | Bonus Checkpoints |
| :----: | :----: |
| ![First Checkpoint | 220](https://i.imgur.com/D0M5eKA.gif)| ![Bonus Checkpoints | 220](https://i.imgur.com/OZ4Azpi.gif)|

Once you are done working on your app, follow the guide in the ‘Submission’ section below to submit your work. Your submission MUST include all the Required Tasks but can also include Optional tasks that you had time to work on.

If you get stuck on implementing a certain task, consult the detailed walkthrough linked at the end of each task.

### Required Tasks

#### 1. Start by opening Android Studio and running your app to make sure everything still works as expected.  

Since it may have been a while since you last loaded your project, we want to ensure that everything still works correctly. Run your app and test that the functionalities you implemented from [lab 2](https://courses.codepath.org/courses/mobile_app_design/unit/4#!labs) still works as expected.  

As a reminder, the basic functionality of your app should be that it :
1) displays a question in text form
2) displays the answer to the question when the question is clicked on
3) allows the user to create their own cards through a separate screen  

#### 2. Add the necessary dependencies to start setting up the app's database

**Concepts / Terminologies introduced** : [Gradle](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_3_glossary.md#heading-gradle), [SQL](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_3_glossary.md#heading-room-persistence-sql)

We'll be using a persistence library called Room to save our app's data. The Room library makes it easy for us to work with a database without having to write SQL queries. In order to start setting this up, we need to add some extra dependencies to our project. Open the `app/build.gradle` file (not the `flashcard/build.gradle`!! There are two separate gradle files and the `app/build.gradle` one is the one to be modified) and add the following lines inside the `dependencies` block and click the 'Sync Now' button that appears in a yellow bar after you modify the `build.gradle` file.

```gradle
def room_version = "2.2.6"

implementation "androidx.room:room-runtime:$room_version"
annotationProcessor "androidx.room:room-compiler:$room_version"
```

^^^
***Click here for additional instructions on how to add the necessary dependencies to prepare for setting up our database***
^^^
First we want to open up our `app/build.gradle` file. We can navigate to it using the `Ctrl + Shift + N` keys combo (or `Cmd + Shift + O` on Macs).

Once you start typing in `build.gradle` in the search bar, you'll notice there are two `build.gradle` files. We want to modify the file under the `/app` directly.

<img src="https://i.imgur.com/mdHwCQM.png" width="600"/>    

In `app/build.gradle`, we want to add the following lines in the `dependencies` block towards the bottom of the file

```gradle
def room_version = "2.2.6"

implementation "androidx.room:room-runtime:$room_version"
annotationProcessor "androidx.room:room-compiler:$room_version"
```

In the end, the `build.gradle` file should look something like this:
<img src="https://i.imgur.com/JtJ8BIN.png" width="700"/>    

You'll notice that Android Studio recognizes that our `build.gradle` file has changed and is now asking us to sync our project again. Click on the Sync button in the yellow bar as shown below.  

<img src="https://i.imgur.com/3TqjwNY.png" width="700"/>  
^^^

#### 3. Create the database related files  

**Concepts / Terminologies introduced** : [Persistence in Android](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_3_glossary.md#heading-persistence-in-android), [Room Persistence Library](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_3_glossary.md#heading-room-persistence-library)

Now that we've added the necessary dependencies to use Room, we can start adding files to set up our database!

Download the following four files to be added to your project. These files should live in the same directory that `MainActivity.java` and `AddClassActivity.java` is in. When you add the files to your project, you'll have to change the first line of each file to your specific package name (because all our apps have different package names!). You can find your package name by looking at the first line in `MainActivity.java`.  

**These files should not be modified at all after you import them and change the package name!**
Download and unzip the files from @[[android/Lab3-code.zip]]

There should be 4 files in the zip:

`Flashcard.java` - This class defines objects that we put in the database. For every field in Flashcard, a column is created in the database  

`AppDatabase.java` - This file creates the actual database. We tell it what kind of objects we are going to put in the database (Flashcard), and how we're planning to access the data (FlashcardDao).

`FlashcardDao.java` - Dao stands for Data Access Objects. This is a fancy way of saying that this class lets us perform SQL queries without actually having to write complicated SQL queries.

`FlashcardDatabase.java` - This is an extra class created to easily interact with the database with helper functions that use FlashcardDao directly.  

^^^
***Click here for more specific instructions on how add the above files to your codebase***
^^^
Click on the following zip @[[android/Lab3-code.zip]] and download the 4 files `Flashcard.java`, `AppDatabase.java`, `FlashcardDao.java`, `FlashcardDatabase.java`


Once the files are downloaded, we can copy the file (`Ctrl + C` or `Cmd + C`) from where they're saved, and then right click on our app package directory to paste the file into the directory.

<img src="https://i.imgur.com/IygD0FS.png" width="400"/>     


Now we have to go into each of the four files to change the package name to be specific to our app. Change the `package com.yourpackage.packagenamehere;` to your app package name.

<img src="https://i.imgur.com/svgSjCs.png" width="400"/>     

You can find your app's package name by opening `MainActivity.java` and looking at the first line in the file.  

<img src="https://i.imgur.com/GfJz51Y.png" width="400"/>     

^^^

#### 4. Allow user to create a card and still see their created card when the app is relaunched.  

<img src="https://i.imgur.com/GGbiKJq.gif" width="220"/>    

Since this lab is centered around persistence with a database, it can be really helpful to see what's currently in the database of your app.

In our last lab session when users created new cards we were only passing data from `AddCardActivity` to `MainActivity` and displaying the data back in `MainActivity`. It wouldn't be very useful if cards that users created were never saved.  

In this step, we want to save the card that the user creates so that when they launch the app again, they can still see the card they just created.  

- In `MainActivity`'s `onActivityResult()`, when we grab the data for the newly created card to display it, we also need to save that data into our database
- In `MainActivity`'s `onCreate()`, we now need to check if there is any data in our database to be displayed.  

Before you move onto implementing this portion of the app, you may want to learn how to view the contents of your app database, you can use the [Android Database Inspector](https://developer.android.com/studio/inspect/database) to inspect the data on your phone in real time. This is helpful for debugging any data storage bugs you might have.

^^^
***Click here for a guide on using the Android database inspector.***
^^^
- Run your current application with the 4 added files copied in on a device that is on API 26 or higher. You should be able to view what API your device/ emulator is on when selecting the emulator to run on, next to the run/ build button.

  <img src="https://i.imgur.com/18AduNg.png" width="400"/>     


- Once the application is running on your device, you can click on `Database Inspector` at the bottom on your android studio. Another way to open the inspector is by searching for it by pressing `Shift-Shift` to search everywhere and typing `Database Inspector`.

  <img src="https://i.imgur.com/fYKbPmc.png" width="600"/>     


- After some time for the database inspector to load your device's database, you should be able to view the `flashcard-database` and double click on `Flashcard` to view the current contents of the database. It should show all the entries you've added to the database. If you have any bugs around displaying using the database, you can use this to figure out if it is a database issue!

  <img src="https://i.imgur.com/ymSD9ky.png" width="600"/>     

- In your database, you should see 5 different columns: `uuid`, `question`, `answer`, `wrong_answer1`, `wrong_answer2`. The `uuid` is a generated string for the database to uniquely identify each entry of data (also known as a row). In the screenshot below we see that there are 2 `Flashcard` objects in the current database. As we add, edit or delete our app local database this will change.

  <img src="https://i.imgur.com/nhpXuN5.png" width="600"/>     

- If you want to ensure you see the contents of the database update when you add/ update your database. Click on the checkmark `Live updates`.

  <img src="https://i.imgur.com/MfGoMJ3.png" width="600"/>     

- Note: there are known issues with Database Inspector when running with an Android 11 emulator. If you're seeing weird errors in your Logcat or your emulator is crashing, [click here to see the troubleshooting guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/pages/troubleshooting/hints_5.md#heading-i-keep-seeing-accessing-hidden-method-errors-in-logcat-or-my-emulator-is-crashing-for-no-reason)

^^^


^^^
***Click here for detailed guide on writing and reading from the app's database to create your first saved card.***
^^^
Recall that in the last lab, users entered data in the `AddCardActivity` to create a new card. The data from `AddCardActivity` was then passed to `MainActivity` through the `onActivityResult` method.  

Now when we process the data in MainActivity's `onActivityResult`, we also want to save that data in our database.

First, we must get an instance of our database so that we can read / write to it. In `MainActivity` , we need the following lines of code to get an instance of the database:

Outside of `onCreate()` create a `flashcardDatabase` variable. Declaring the variable outside of a method allows us to access this variable in all methods of `MainActivity`):

```java
FlashcardDatabase flashcardDatabase;
```

Inside `onCreate()` method, we will initialize the flashcardDatabase variable.
We have to do this inside `onCreate()` method because `getApplicationContext()` will return null if the app hasn't initialized yet. And in `onCreate()` we can guarantee that the app has been initialized:

```java
flashcardDatabase = new FlashcardDatabase(getApplicationContext());
```

From the last lab, your `onActivityResult` probably looks something like this:

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    if (requestCode == ADD_CARD_REQUEST_CODE) {
        String question = data.getExtras().getString("question");
        String answer = data.getExtras().getString("answer");

        ((TextView) findViewById(R.id.flashcard_question)).setText(question);
        ((TextView) findViewById(R.id.flashcard_answer)).setText(answer);
    }
}
```

Once we have our database instance, in `onActivityResult()` we can add this line to save a flashcard:

```java
flashcardDatabase.insertCard(new Flashcard(question, answer));
```

where the variable `question` is the data we extracted from `data.getExtras().getString("question")` and the variable `answer` is the data we extracted from `data.getExtras().getString("answer");`

We also want to update our list of flashcards now that a new flashcard has been added, otherwise when we browse through multiple cards it will appear as if the newly created card wasn't saved.

In `MainActivity`, let's create a variable to hold all our flashcard objects. Outside of `onCreate`, declare a variable to hold a list of Flashcards like so:  

```java
List<Flashcard> allFlashcards;
```  

Now back in MainActivity's `onActivityResult`, we want to add this line so that our local variable holding the list of flashcards is updated:

```java
allFlashcards = flashcardDatabase.getAllCards();
```

**Now we are officially saving data to our database! The next step is to read from the database when the app is launched.**

Inside MainActivity's `onCreate()`, AFTER the `flashcardDatabase` variable initialization, we can access the cards like so:

```java
allFlashcards = flashcardDatabase.getAllCards();
```

Once we have the list of flashcards saved in our database, we can check to see whether the list is empty. If it's not empty, we can display the saved flashcard. You should write this if statement in your `onCreate()` method to display the question & answer text. This way whenever `MainActivity` is first created it'll first check the database to see if there's any saved flashcards before displaying the default one that was populated from `main_activity.xml`.

At this point, you should be able to create a flashcard, close the app, and see the flashcard you just created when you relaunch the app!

^^^

This is the most complicated part of the app we will build and a lot of small things can cause this step to end up buggy. Reach out to your classmates if your code doesn't work as expected after your implementation.


^^^
*This is what your code should look like after following the guide. Only click here if you've already followed the above guide and would like more guidance!*
^^^

`MainActivity` variable instantiation

```java
FlashcardDatabase flashcardDatabase;
List<Flashcard> allFlashcards;
```

`MainActivity onCreate()`

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    flashcardDatabase = new FlashcardDatabase(this);
    allFlashcards = flashcardDatabase.getAllCards();

    if (allFlashcards != null && allFlashcards.size() > 0) {
        ((TextView) findViewById(R.id.flashcard_question)).setText(allFlashcards.get(0).getQuestion());
        ((TextView) findViewById(R.id.flashcard_answer)).setText(allFlashcards.get(0).getAnswer());
    }
    // more code below not shown
```

`MainActivity onActivityResult()`

```java
@Override
 protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
    if (requestCode == ADD_CARD_REQUEST_CODE && resultCode == RESULT_OK) {
        String question = data.getExtras().getString("question");
        String answer = data.getExtras().getString("answer");

        ((TextView) findViewById(R.id.flashcard_question)).setText(question);
        ((TextView) findViewById(R.id.flashcard_answer)).setText(answer);

        flashcardDatabase.insertCard(new Flashcard(question, answer));
        allFlashcards = flashcardDatabase.getAllCards();
    }
 }
```

^^^

#### 5. User should be able to create multiple cards and browse through their deck of created cards  

<img src="https://i.imgur.com/D0M5eKA.gif" width="220"/>    

- Find and add an icon to be used as the 'next' button.
- Set an `onClickListener` for the 'next' button so that whenever the button is clicked, the app displays a new card from the database (if there is only one card saved in the database, then the app won't show anything new)  

^^^
***Click here to view out the detailed guide allowing users to browse through multiple cards***
^^^
In order to show the 'next' card in our list of saved cards, we need to create a variable to keep track of the index of the current card we're showing.

Let's create another variable named `currentCardDisplayedIndex` and set it to 0 since we will always start by showing the first card in our list of cards:

```java
int currentCardDisplayedIndex = 0;
```

With that variable created, back inside the `onCreate()` method we can now set an `onClickListener` for our 'next' button. Fill in the code below each comment

```java
findViewById(R.id.next_button).setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
    // advance our pointer index so we can show the next card

    // make sure we don't get an IndexOutOfBoundsError if we are viewing the last indexed card in our list

    // set the question and answer TextViews with data from the database
});
```

^^^


^^^
*This is what your code should look like after following the guide. Only click here if you've already followed the above guide and would like more guidance!*
^^^

`MainActivty.java` within `onCreate`

```java
findViewById(R.id.nextBtn).setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View v) {
          // don't try to go to next card if you have no cards to begin with
          if (allFlashcards.size() == 0)
              return;
          // advance our pointer index so we can show the next card
          currentCardDisplayedIndex++;

          // make sure we don't get an IndexOutOfBoundsError if we are viewing the last indexed card in our list
          if(currentCardDisplayedIndex >= allFlashcards.size()) {
              Snackbar.make(questionSideView,
                      "You've reached the end of the cards, going back to start.",
                      Snackbar.LENGTH_SHORT)
                      .show();
              currentCardDisplayedIndex = 0;
          }

          // set the question and answer TextViews with data from the database
          allFlashcards = flashcardDatabase.getAllCards();
          Flashcard flashcard = allFlashcards.get(currentCardDisplayedIndex);

          ((TextView) findViewById(R.id.flashcard_question)).setText(flashcard.getAnswer());
          ((TextView) findViewById(R.id.flashcard_answer)).setText(flashcard.getQuestion());
      }
  });
```

^^^

## Submitting Your Lab Project

 Once you have finished all the required tasks and pushed your code to GitHub you'll need to submit your project. If you decide to take on some of the optional feature challenges
1. Create a README in your GitHub repository and paste in the contents of this **[Lab 3 README Template](https://courses.codepath.org/snippets/mobile_app_design/readme_templates_android/03_lab_3_readme.md?raw=true)**
1. In the README, mark off all the features you implemented, using the following syntax`-[x]`
1. Record a GIF walkthrough of your app that showcases the features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
   :::info
  Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/5018a550a802fde19610f444c329b091)** to see what a completed README should look like.
  :::

### Optional Tasks

#### 1. User should be able to delete a card and no longer see it in their deck anymore  

[Empty States](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_3_glossary.md#heading-empty-states)

<img src="https://i.imgur.com/xODXo7n.gif" width="220"/>    

- Find and add an icon to be used as the 'trash' button.
- Set an `onClickListener` for the 'trash' button so that whenever the button is clicked, the app :
  - Deletes the currently displayed card
  - Shows the previous card in the deck (if there is one)
  - Shows an empty state if there are no more cards left in the database  

^^^
***Click here for a detailed guide on deleting a card from the database here***
^^^
If we look at `FlashcardDatabase.java`, we can see the `delete()` method takes in a string as a parameter, and that string should be the Question of the flashcard we want to delete. (The method will delete the whole flashcard instance, but passing in only the question is a nice convenience.)  

Knowing that, we can set our onClickListener for the 'delete' button to be something like:

```java
findViewById(R.id.deleteBtn).setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        flashcardDatabase.deleteCard(((TextView) findViewById(R.id.flashcard_question)).getText().toString());
    }
});
```

The above code deletes the flashcard from the database, but there are still a couple of things we have to handle:

1. update our instance of list of cards: `allFlashCards`. If you recall, we first set this variable in `onCreate()` :

    ```java
    allFlashcards = flashcardDatabase.getAllCards();
    ```  

    This means that this variable was only set during onCreate(), so now that we've deleted a card, we need to update the `allFlashcards` variable with the same line of code. Otherwise, `allFlashcards` will be holding on to stale data!  

2. We need to build some logic to update the `currentCardDisplayedIndex` variable so that the next time the 'next' button is clicked, we see the correct card.  

3. If there are any cards left in the database, we want to show a card from the database. However, if there are not any cards left in the database, we want to show an 'empty' state. This 'empty' state can be text that prompts the user to add a new card (in which case, we would update the question TextView to display something like "Add a card!"), or it can be an image!  

If you're looking for some 'empty state' inspirations, check out http://emptystat.es/  
^^^

#### 2. Randomize the order in which the cards are shown

- Create a `getRandom(int minNumber, int maxNumber)` function that takes in a min and a max, and returns a random number between min and max inclusive.
- Modify the `onClickListener` for the 'next' button so that it retrieves a random card to show instead of simply showing the next card in the list of cards  

^^^
***Click here for a detailed guide on generating a random card***
^^^
An easy way to get a random number in java is with the following function:

```java
// returns a random number between minNumber and maxNumber, inclusive.
// for example, if i called getRandomNumber(1, 3), there's an equal chance of it returning either 1, 2, or 3.
public int getRandomNumber(int minNumber, int maxNumber) {
    Random rand = new Random();
    return rand.nextInt((maxNumber - minNumber) + 1) + minNumber;
}
```  

Add this method inside your `MainActivity` to use it in the onClickListener for the 'next' button.

Note: You may want want to regenerate the number if it's the same number as the current index, so it doesn't show the same card again when you press next!

If you recall, previously we were keeping track of which card to show next with a variable we created: `currentCardDisplayedIndex`. Now that we want to show flashcards in random order, we don't need that variable anymore, and instead we should use the number returned from `getRandomNumber()`
^^^

#### 3. (Difficult optional!) User should be able to edit a card and see the edit saved when they browse through their deck of cards   

(In the following example, I only have 2 cards saved. "Who is the 16th president?" and "Who's on the $10 bill". I then edit the first card from "Who is the 16th President" -> "Who is the 32nd President" and changed the answer from Abraham Lincoln -> Franklin D. Roosevelt)  

<img src="https://i.imgur.com/OZ4Azpi.gif" width="220"/>    

** This requires you to have done the first optional in the last lab. Head on over and implement the first optional feature from [this lab](https://courses.codepath.org/courses/mobile_app_design/unit/4#!labs) if you haven't already done so.  

^^^
***Click here to see the detailed guide on how to edit entries in a database.***
^^^
The first thing we want to do is add a new REQUEST_CODE. Recall that when the 'add' button is clicked, we start `AddCardActivity` with a unique REQUEST_CODE, so that in `onActivityResult()` we can know how to handle the result:

```java
Intent myIntent = new Intent(MainActivity.this, AddCardActivity.class);
MainActivity.this.startActivityForResult(myIntent, ADD_CARD_REQUEST_CODE);
```  

We had used the same ADD_CARD_REQUEST_CODE when the 'edit' button is clicked. But now we need to distinguish whether we want to add a new card, or edit an existing card. So we must create a new EDIT_CARD_REQUEST_CODE and use that to start `AddCardActivity` :

```java
Intent myIntent = new Intent(MainActivity.this, AddCardActivity.class);
MainActivity.this.startActivityForResult(myIntent, EDIT_CARD_REQUEST_CODE);
```  

Going inside `FlashcardDatabase.java` we can see that the `updateCard()` method takes in a `Flashcard`. This means that we need to pass a `Flashcard` object to the method when we want to update an existing card.  

In order to know which Flashcard to update, we should save the Flashcard instance that's currently being displayed when the 'edit' button is clicked. There are multiple ways to do this, and you should feel free to come up with your own solution! For those curious, the solution I went with is something like the following:  
1) I created a new variable outside of the `onCreate()` method: `Flashcard cardToEdit;`  
2) In the `onClickListener` for the 'edit' button, I look at the current Question being displayed in the TextView. I then loop through the list of all cards (`allFlashCards`) to find the one that has the same question as the current Question being displayed. I then set `cardToEdit` to the matching Flashcard.  
3) This way, when we come back to `MainActivity`, I have a variable `cardToEdit` that's been populated with the card that I want to edit.  

Now in our `onActivityResult()` method we need to add an `else if` case for handling the new EDIT_CARD_REQUEST_CODE. So our `onActivityResult()` method would look something like:

```java
@Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        if (requestCode == ADD_CARD_REQUEST_CODE && resultCode == RESULT_OK) {
            // grab the data passed from AddCardActivity
            // set the TextViews to show the new question and answer

            flashcardDatabase.insertCard(new Flashcard(question, answer));

        } else if (requestCode == EDIT_CARD_REQUEST_CODE && resultCode == RESULT_OK) {
            // grab the data passed from AddCardActivity
            // set the TextViews to show the EDITED question and answer

            cardToEdit.setQuestion(question);
            cardToEdit.setAnswer(answer);

            flashcardDatabase.updateCard(cardToEdit);
        }
    }
```

Notice that can change the 'question' or the 'answer' of the flashcard by calling setter methods. For example, if I wanted to change the question, I can do so with the following:

```java
cardToEdit.setQuestion("Who was the 3rd President of the United States?");
```

After setting the question for the flashcard, I can then update the database :

```java
flashcardDatabase.updateCard(cardToEdit);
```

^^^

#### 4. (Difficult optional!) Multiple choice

** This requires you to have done optionals from the first and second lab. Check out the optional features regarding Multiple Choice in [Lab 1](https://courses.codepath.org/courses/mobile_app_design/unit/2#!labs) and [Lab 2](https://courses.codepath.org/courses/mobile_app_design/unit/4#!labs) if you haven't already implemented them.

If you've done the Multiple Choice feature from the previous labs, you can also save flashcards with multiple choice answers in the database.  

Notice that in `Flashcard.java` there's another constructor that takes in wrong answers for the question as well.

```java
Flashcard(String question, String answer, String wrongAnswer1, String wrongAnswer2) {

```

You can utilize this constructor when users add cards to also save the wrong answers in the database to be used.

### Re-submitting Your Lab Project After Completing Optional Features

 Anytime you complete more optional features for your app, you'll need to update your submission and re-submit.
1. Update your README by marking off any additional optional features you implemented, using the following syntax`-[x]`
1. Record a new GIF walkthrough that showcases the new features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
1. Submit your app using the same **Submit** button found at the top of this lab page.
 :::info
Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/5018a550a802fde19610f444c329b091)** to see what a completed README should look like.
:::
