# Lab 3 : Saving Flashcard Trouble Shooting Guide

Here are some common problems / bugs you may encounter while working through the lab to implement the necessary features to save your flashcards and browse through them.

If you don't see your issue listed here **ping the mad-android slack channel or one of the instructors / TAs** so we can help you resolve the issue!  

If you are working on the lab and have been **stuck on an issue for more than an hour or two**, please be sure to reach out in order to get unblocked.

- [I can't see the card I just saved after I relaunch my app](#heading-i-cant-see-the-card-i-just-saved-after-i-relaunch-my-app)
- [When I save my card, I can see it when I go back to MainActivity, but then the card seems to disappear after I browse through multiple cards](#heading-when-i-save-my-card-i-can-see-it-when-i-go-back-to-mainactivity-but-then-the-card-seems-to-disappear-after-i-browse-through-multiple-cards)
- [When I click the 'Next' button the app crashes / closes](#heading-when-i-click-the-next-button-the-app-crashes-closes)
- [I keep seeing `Accessing hidden method` errors in logcat. Or my emulator is crashing for no reason](#heading-i-keep-seeing-accessing-hidden-method-errors-in-logcat-or-my-emulator-is-crashing-for-no-reason)

### I can't see the card I just saved after I relaunch my app  

- Check whether that card was actually saved to the database. You can see the contents of your database by following the step [here](https://courses.codepath.com/courses/mobile_app_design/pages/android/walkthroughs/lab3_walkthrough.md#heading-set-up-for-viewing-the-contents-of-your-apps-database).

  If you don't see the card saved in your database, that means you're missing this crucial line in `onActivityResult()`:

  ```java
  flashcardDatabase.insertCard(new Flashcard(question, answer));
  ```

- Are you reading from the database when the app is relaunched? In your MainActivity's onCreate(), you should be reading from the database like so: `allFlashcards = flashcardDatabase.getAllCards();`  


### When I save my card, I can see it when I go back to MainActivity, but then the card seems to disappear after I browse through multiple cards  

Recall that we started by creating a variable to hold the list of flashcards that are saved in the database :

```java
List<Flashcard> allFlashcards = flashcardDatabase.getAllCards();

```

In `onCreate()` we had added the line `allFlashcards = flashcardDatabase.getAllCards()` to store the list of flashcards. However, whenever the database is updated, we also need to update our local variable `allFlashcards`.

There are two things to check in this case:
1) on `onActivityResult()`, did you update the list of flashcards again?
2) if you did update the list of flashcards again, does that call come AFTER the call to add the card to the database? In other words, the order in `onActivityResult()` should be:

```java
flashcardDatabase.insertCard(new Flashcard(question, answer));
allFlashcards = flashcardDatabase.getAllCards();

```

### When I click the 'Next' button the app crashes / closes  

The first thing to do would be to check the crash logs to see what caused the crash, and you can get an overview of how to do that here: https://courses.codepath.com/courses/mobile_app_design/pages/android/android_studio_intro.md#heading-looking-for-crash-errors  

First, it's worth checking if you did step two in [this troubleshooting step](#heading-when-i-save-my-card-i-can-see-it-when-i-go-back-to-mainactivity-but-then-the-card-seems-to-disappear-after-i-browse-through-multiple-cards)

Next, the crash was likely caused by an IndexOutOfBounds error. This means that the app was trying to access a flashcard that doesn't exist.  

For example, if we currently have 3 cards saved, but the app tries to access a 4th card. To fix this, you'll have to add in a check to make sure that the app doesn't trie to grab a '4th' card when there's only 3 cards saved. Instead of accessing the '4th' card, you should reset the index to be 0, so the app can cycle through the cards again.


### I keep seeing `Accessing hidden method` errors in logcat. Or my emulator is crashing for no reason

This error happens due to using the database inspector with the emulator. There is a fix which requires you to install the most up to date revision of the Google Play System image.
If you see `Accessing hidden field Landroid/database/sqlite/SQLiteDatabase` you can ignore these errors.

If you see `Fatal signal 11 (SIGSEGV), code 1 (SEGV_MAPERR)`, or your emulator crashes unexpectedly see [Android Studio Known Issues: Apps using the database inspector crash on Android 11 emulator](https://developer.android.com/studio/known-issues#ki-android-11-db-inspector).
