# Lab 1: Flashcard App

## Goals

- Create a new app project
- Add different UI views on a screen
- Customizing UI
- Understand how to debug crashes and log useful messages
- Push project to Github

**Before you start the lab, it may be a good idea check out these two resources:**


1. [Android Studio Starter Guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/android_studio_intro.md)
2. [The Skills Tab](https://courses.codepath.org/courses/mobile_app_design/unit/2#!skills) to get a quick overview of the new concepts introduced in this lab
3. [Android Troubleshooting Guide](https://hackmd.io/s/r1KlxitOX) - Check here first if your emulator or Android Studio isn't working!

## Introduction

Refer to this video for an introduction to the concepts you'll encounter in this lab:

<iframe width="640" height="316"  src="https://www.youtube.com/embed/fkWot7tcSIU?list=PLrT2tZ9JRrf47Ti_eQjzpZVHLE43kMgZX" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- [Lab 1 Lecture Slides](https://speakerdeck.com/marusya82/mad-week-2-lab-1)

## Challenge

Each technical lab has a section of Required and Optional Tasks. Required Tasks MUST be completed as part of your submission, but if you finish those tasks early, feel free to explore the Optional Tasks.

This week we will start building our Flashcard app. By the end of this lab you should have a basic Flashcard app that can:

- display a question
- respond to a user's tap to display the answer to the question

This is what the flashcard will look like at the end of this lab:

| First Checkpoint | Bonus Checkpoints |
| :----: | :----: |
| ![First Checkpoint | 220](https://i.imgur.com/GX3Yfii.gif)| ![Bonus Checkpoints | 200](https://i.imgur.com/qP9FLRg.gif)|

We will also practice pushing code to Github in order to better manage the project.

Once you are done working on your app, follow the guide in the ‘Submission’ section below to submit your work. Your submission MUST include all the Required Tasks but can also include Optional tasks that you had time to work on.

^^^
***For every task, there is a more detailed walkthrough guide linked at the end of the task description. You can click text that looks like this, to show/ hide the detailed walkthrough.***
^^^
Great! This would be where the detailed walkthrough would be.
^^^


### Required Tasks

#### 1. Create New Project in Android Studio

**Concepts / Terminologies introduced** : [minSDK](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-minsdk-version) , [Android's Activity](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-activity)



- Open Android Studio and create a new android project
- Choose to create an 'Empty Activity'

  ![Select New Project | 500](https://i.imgur.com/TF2fjWr.png)

- be sure to give your app a good name (it doesn't have to be Flashcard)!
- change to "Java" instead of "Kotlin" as the coding language
  ![Configure your Project | 500](https://i.imgur.com/6WlDtQL.png)

- once the project has been successfully created, run your app to make sure you can see the default ` Hello World! ` screen

  Notice that when you created the project, Android Studio automatically generates a lot of files. You should see this on the left side navigation. (If you don't see the navigation bar, click Project -> and make sure "Android" is selected at the top left corner.) The two most important ones that we care about right now are `MainActivity.java` and `activity_main.xml`.

  ![Navigation Bar | 300](https://i.imgur.com/qxWBOSV.png)

  *Pro Tip: You can also use `Command+Shift+O` on Mac or `Control+Shift+N` on Windows to navigate to the file you want without using the navigation drawer. You can also use the target icon highlighted in the above screenshot on the navigation drawer to highlight the file you're currently on in the navigation drawer.*


#### 2. Add a view for the front side of the flashcard to display the question

![Imgur](https://i.imgur.com/mr90Znr.png)

**Concepts / Terminologies introduced** : [xml](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-xml), [RelativeLayout / ConstraintLayout](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-relativelayout-and-constraintlayout), [Android's Views](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-view), [Android's TextView](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-textview), [dp vs sp](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-dp--sp), [id](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-id), [match_parent](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-match_parent)

Recall that `activity_main.xml` is the layout file where we can add, position, and style different views and that `TextView` is a specific type of view used in Android layouts to display text, much like how `Button` and `ImageView` are other specific types of Android views.  

**If you are not able to see a preview of your layout, [click here to go to the troubleshooting page](https://courses.codepath.org/courses/mobile_app_design/pages/android/pages/troubleshooting/hints_2.md#heading-fixing-layout-preview-not-showing)**

- For this step, we'll be working with the `activity_main.xml` file. Since this was autogenerated,  we need to modify it a bit.
  - The root view in `activity_main.xml` is currently `ConstraintLayout`. Change it to be `RelativeLayout` instead
  - Delete the autogenerated "Hello World!" `TextView`
- Add our own `TextView` and customize it with the appropriate dimension and text
  - give the `TextView` a more appropriate id name such as `flashcard_question` to help us identify it later
  - adjust the `TextView`'s dimensions so that it takes up the whole width of the screen (`match_parent`) and has a height of `200dp`
  - populate the `TextView` with text so that it displays a question
  - make the text more readable by increasing the font size to `40sp`
  - center the text
- run your app to make sure you can see the question displayed

^^^
***Click here for a detailed guide on how to add this custom text view.***
^^^

- To add a TextView to our layout, we must first navigate to the `activity_main.xml` file. One way to do this is with the file navigator. Layout files are under App -> res -> layout.  

<img src="https://i.imgur.com/3KAKR6j.gif" width="1000"/>  

The other way to do this is to use the file navigator shortcut (`Ctrl + Shift + N` on Windows or `Command + Shift + O` on Mac) and start typing in the file name.  

- Edit our layout file `activity_main.xml` to be a `RelativeLayout` instead
  - Our auto-generated layout is a `ConstraintLayout` right now. Let's change it to `RelativeLayout` for our purposes by changing any text that says `ConstraintLayout` to `RelativeLayout`. We should also take out the prepopulated TextView that says "Hello World!"

  Before:  

  <img src="https://i.imgur.com/Dl9EOay.png" width="500" />  

  After:  

  <img src="https://i.imgur.com/Bxcx4Xk.png" width="500" />  

  <br>
  <br>

  - Switch to the Design tab in the layout editor to prepare for adding the TextView  

  <br>
  <img src="https://i.imgur.com/SMwux5P.png" width="600" />    
  <br>
  <br>

  - We can add a TextView to our layout by dragging and dropping a TextView in the layout editor  

  <br>
    <img src="https://i.imgur.com/O99y3VH.gif" width="800" />    

- Set the id name of the TextView we just created to `flashcard_question` (if your option for "View XML Attributes" is toggled off, you might have a slightly different view)
    <img src="https://i.imgur.com/EfQaRoF.png" width="600" />    

- Adjust the TextView's dimensions to take up the whole width of the screen with a height of `200dp`  
    <img src="https://i.imgur.com/RjOwbZk.png" width="600" />    

- Populate the TextView with a question
  - In the same panel where we edited the height and width of the TextView, look for the field `android:text`. It's current value should be "TextView". Change the text so that it displays a question instead.

- Increase the font size of the TextView to 40sp
  - Switch from the Design view back to the Text view so that we can work with the XML file directly. Notice that all the changes we've been making in the Layout Editor have been translated to XML in this file. Make sure your TextView block looks like the following and doesn't have any extra attributes defined (like margins, or alignments)

  To specify the size of the text, we have to add the attribute `android:textSize="40sp"`.  

  Notice that when setting sizes for height and width we used `dp` and for setting text sizing we used `sp` .

- Center the Text

  - Different views have different methods of centering content. For TextViews, the attribute we're looking for is `android:gravity` . Add this attribute to the TextView and set its value to `center`.

- Wondering why your `android:text` is highlighted in yellow on Android Studio? [Click here to learn more](https://courses.codepath.org/courses/mobile_app_design/pages/android/pages/troubleshooting/hints_2.md#heading-why-does-is-my-androidtext-xml-code-highlighted-in-yellow)

^^^

^^^
*This is what your xml code should look like. Only click here if you've already followed the above guide!*
^^^

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/flashcard_question"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:gravity="center"
        android:text="Who is the 44th President of the United States?"
        android:textSize="40sp" />
</RelativeLayout>
```  

^^^


#### 3. Add a view for the back side of the flashcard to display the answer

![Imgur](https://i.imgur.com/eFr2fef.png)

- Similar to how we created the `TextView` for the question in the previous step, add another `TextView` to the layout and populate the text with the answer to the question.
- Move the answer text view to be below the question text view so we can see both on the screen.
- Run your app to make sure you can see both the question and the answer texts

^^^
***Click here for a detailed guide on how add a new TextView and position it***
^^^
- Since the new TextView we want to add is almost identical to the last TextView we added, we can copy and paste the block of code from the `flashcard_question` TextView   
- Notice that after copy and pasting, there will now be a red squiggly line

<img src="https://i.imgur.com/D47q9Us.png" width="600" />    

When you see these red squiggly lines, it's Android Studio's way of telling you that there will be a compile error. This means you will not be able to build and run your app.

In order to fix this error, we should change the id of the new TextView we added to `@+id/flashcard_answer` instead of `@+id/flashcard_question`

- If you're looking at the preview of the layout, you'll notice that the two TextViews overlap each other right now, making it hard to read either one. We can fix this by positioning `flashcard_answer` to be under `flashcard_question` with the attribute `android:layout_below="@id/flashcard_question"`
^^^

^^^
*This is what your xml code should look like. Only click here if you've already followed the above guide!*
^^^

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/flashcard_question"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:gravity="center"
        android:text="Who is the 44th President of the United States?"
        android:textSize="40sp" />

    <TextView
        android:id="@+id/flashcard_answer"
        android:layout_below="@id/flashcard_question"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:gravity="center"
        android:text="Barack Obama"
        android:textSize="40sp" />
</RelativeLayout>
```

^^^

#### 4. Build in logic to show the answer side when the card is tapped

**Concepts / Terminologies introduced** : [Listeners](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-listener)

<img src="https://i.imgur.com/GX3Yfii.gif" width="200"/>

Recall that certain Listeners in Android allow us to handle user interactions within our app. `OnClickListener` is the most commonly used type of Listener that allows us to know when the user does a single tap in our app. When the user taps on a view  if the view has an attached `OnClickListener`, the `OnClickListener` will be called and the code within the `OnClickListener` will be executed.

- since we don't want to show the question and the answer at the same time anymore, now we should move the answer text view to be at the same location as the question text view
- set the visibility of the answer text view to be invisible so it doesn't block the question text
- set an onClickListener for the question text view that will hide the question text view and show the answer text view
- run your app to test that when you click on the question, the answer text appears

^^^
***Click here for a more detailed guide on adding click handlers***
^^^
- We want to show `flashcard_answer` after the user clicks on the card, as a result, we actually don't want `flashcard_answer` to be below `flashcard_question`.  Let's remove the line `android:layout_below="@id/flashcard_question"` from `flashcard_answer`.

- Notice that now `flashcard_answer` covers `flashcard_question` now. Since we only want to show `flashcard_answer` when the user clicks on the card, we have to hide it initially. We can achieve this by setting `android:visibility` to be `invisible` for `flashcard_answer`.

- In order to add logic for when the card is clicked, now we have to navigate to the `MainActivity.java` class. The common way to attach a click event to a view is as such:  

```java
findViewById(R.id.nameOfView).setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Do something here    
    }
});
```

*This block of code needs to be inside the `onCreate()` method! If it's not inside `onCreate()`, Android Studio will start complaining.*

- In the above code, when the view with the id `nameOfView` is clicked, the code inside the `onClick` block is executed. In this case, we don't have anything inside the block, so nothing will happen.

- Since we want to show `flashcard_answer` and hide `flashcard_question` onClick, we should set the visibility of these views inside the onClick block.  

- We can set the visibility of a view with code such as : `findViewById(R.id.flashcard_answer).setVisibility(View.VISIBLE);`  

- Using the same pattern and with the example from above, set `flashcard_answer`'s visibility to `View.VISIBLE` and `flashcard_question`'s visibility to `View.INVISIBLE` when the card is clicked.
^^^

^^^
*This is what your MainActivity.java code should look like. Only click here if you've already followed the above guide!*
^^^

```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView flashcardQuestion = findViewById(R.id.flashcard_question);
        TextView flashcardAnswer = findViewById(R.id.flashcard_answer);
        flashcardQuestion.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                flashcardQuestion.setVisibility(View.INVISIBLE);
                flashcardAnswer.setVisibility(View.VISIBLE);
            }
        });
    }
}
```

^^^

#### 5. Push code to Github

**Concepts / Terminologies introduced** : [Github](https://courses.codepath.org/courses/mobile_app_design/pages/android/glossary/lab_1_glossary.md#heading-github)

Now that we have the first version of our app implemented, we should push our project to Github to save our progress.

- Create a new repository on Github and push your project

  For a more detailed guide on using Github within Android Studio, take a look at this [Github  how to guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/github_how_to.md).

## Submitting Your Lab Project

Once you have finished all the required tasks and pushed your code to GitHub you'll need to submit your project. If you decide to take on some of the optional feature challenges

1. Create a README in your GitHub repository and paste in the contents of this **[Lab 1 README Template](https://courses.codepath.org/snippets/mobile_app_design/readme_templates_android/01_lab_1_readme.md?raw=true)**
1. In the README, mark off all the features you implemented, using the following syntax`-[x]`
1. Record a GIF walkthrough of your app that showcases the features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.

  :::info
  Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/1e2b05bb74cf9867a4212def64a810fc)** to see what a completed README should look like.
  :::

### Optional Tasks

#### 1. Build in logic to toggle the flashcard between the question side and the answer side

<img src="https://i.imgur.com/F9bUfzG.gif" width="200" />

- Similar to how we added an onClickListener to the `flashcard_question` view, we can add another onClickListener to `flashcard_answer` to achieve the toggling effect
- The onClickListener for `flashcard_answer` should handle setting the visibility for `flashcard_question` and `flashcard_answer`

  ** `OnClickListener`'s need to be correctly attached to the view that wants to listen for user actions and this can be tricky when there are multiple views that have different listeners. Ask your breakout room members for help debugging if you weren't able to achieve the toggling effect.

#### 2. Style the question and answer side of the card to better distinguish between the two sides

<img src="https://i.imgur.com/ezgXEJX.gif" width="200" />

- Add a background color and text color for the question card view
- Add a different background color and different text color for the answer card view

^^^
***Click here for detailed instructions on customizing background and text colors.***
^^^
- Adding and customizing colors for views is typically done in the XML layout file. Each view in the XML can have a `android:background` property. For example, if we added the following line to a TextView `android:background="#000000"`, the background of the TextView would be set to black because `#000000` is the hex code for the color black.  

- Similarly, the text color in a TextView can be set with the `android:textColor` property. For example, if we wanted to set a text to be white, we would add the following line to the TextView `android:textColor="#ffffff"`

^^^

#### 3. Further customize and style the card

<img src="https://i.imgur.com/T92I0EY.png" width="200" />

- Create a custom [Shape Drawable](https://guides.codepath.org/android/drawables#drawing-shapes) to give the card:

  - rounded corners
  - colored border
  - custom background color

- Give the card a [shadow/elevation](https://developer.android.com/training/material/shadows-clipping#shadows) effect

- If we want the question side and the answer side of the card to be stylized differently, we will have to create two separate Drawables and set them as the views backgrounds individually

^^^
***Click here for a more in-depth walkthrough of advanced customizations.***
^^^
- In order to give a view rounded corners, a border, and a custom background, we need to create a custom shape drawable.
  - Navigate to the drawable folder, and then right click to create a new 'Drawable Resource File' and name the new file `card_background`

      <img src="https://i.imgur.com/Mg3sB9L.png" width="600"  />    
  - We now have a `card_background.xml` file that's very similar to the `activity_main.xml` file we've been working with.
  - Copy and paste this block of code into your `card_background.xml` file

    ```xml
      <?xml version="1.0" encoding="utf-8"?>
      <shape xmlns:android="http://schemas.android.com/apk/res/android"
        android:shape="rectangle">
        <corners android:radius="10dp" />
        <stroke android:color="#000000" android:width="6dp" />
        <solid android:color="#ffffff" />
      </shape>
    ```

  - If you have the preview window open, you should now see a white rectangle with a black rounded corners border.
  - Experiment with the hex values and the dimensions to achieve the card look you want
    - `<corners android:radius="10dp" />` the number defined here changes how 'rounded' the corners are.
    - `<stroke android:color="#000000" android:width="6dp" /> ` this is the definition for the border. The `color` attribute sets the color of the border and the `width` attribute defines the thickness of the border
    - `<solid android:color="#ffffff" />` defines the background color of the shape
- Once we've created our custom drawable, we need to add it as the background for our card.
  - Navigate back to `activity_main.xml` and set the background attribute of `flashcard_question` to be the new drawable we just created
    - `android:background="@drawable/card_background"`
- We can also add a elevation attribute to `flashcard_question` to give it the shadow effect.
  - `android:elevation="5dp"` . The larger the number, the more shadow will appear.
^^^

#### 4. Add selectable multiple choice answers beneath the card

<img src="https://i.imgur.com/NQW7uON.png" width="200" height="400" />

- Add 3 additional `TextView`'s under the question/answer card. We should use properties of the `RelativeLayout` to achieve this.

  For more detailed instructions on working with RelativeLayouts, check out this [guide on constructing relative layouts](https://guides.codepath.org/android/Constructing-View-Layouts#relativelayout).

#### 5. Change the background color of the multiple choice answers when clicked to indicate whether the question was answered correctly

Note: The GIF above is looping through 3 different scenarios. You don't have to build any type of 'reset' logic.
<img src="https://i.imgur.com/k5CKb4N.gif" width="200"/>

- Add onClickListeners to each of the 3 additional `TextView`s we previously added and put in logic to change the background colors for the different TextViews accordingly

^^^
***Click here for detailed instructions on how to set a view's background color dynamically.***
^^^
- Similar to how we set onClickListeners for views, we can also change properties for views through our Java code. For example, we can change a view's background color to our custom red color with the following line

```java
findViewById(R.id.myView).setBackgroundColor(getResources().getColor(R.color.my_red_color, null));
```

We would have to define `R.color.black` in `colors.xml`. If we navigate to the `colors.xml` file in `src/main/res/values/colors.xml`, we can see that there are already 3 colors defined. In this file we can define any additional colors we want. For example, if we wanted to add a red color , we can do so by adding the line `<color name="my_red_color">#ee0000</color>`
^^^

#### 6. Add a button that will toggle hiding and showing the answer choices

<img src="https://i.imgur.com/qP9FLRg.gif" width="200" />

Note : Notice that whenever the 'eye' icon is clicked, it also switches state based on whether the answer choices are showing or not. When the answers are showing, the 'eye' icon has a diagonal line through it to indicate that clicking on it will hide answers. When the answers are not showing, the 'eye' icon indicates that clicking on it will show answers.

^^^
***Click here for more info on how to add icons and change them dynamically***
^^^
- First we need to download the icons we want to use. https://iconmonstr.com/ is a great resource.
- When downloading icons, if SVG is an option, that's the preferred format to download. PNG or JPEG would also work
- After the icon is downloaded, we have to import it into our project. If you downloaded a SVG, you want to import a Vector Asset. If you downloaded a PNG or JPEG, you want to import an Image Asset. The screenshot below is for when you've downloaded a PNG or JPEG. For SVGs, you would select the option below it (Vector Asset)

<img src="https://i.imgur.com/88Z973W.png" width="700"/>  

- Once you've selected which kind of asset to import, look for the Path field. Edit this field so that it points to the location of where you downloaded the icon.  
- Be sure to give your icon a suitable name that will help you identify it later

- Now we must use an `ImageView` in our `activity_main.xml` to display our icon.

```xml
<ImageView
    android:layout_width="40dp"
    android:layout_height="40dp"
    android:id="@+id/toggle_choices_visibility"
    android:src="@drawable/hide_icon"/>
```

- Notice the line `android:src="@drawable/hide_icon"`. `hide_icon` should match the file name of the icon you imported in order for Android to know which resource to use
- We also want this icon to be aligned to the bottom center of the screen. Experiment with the different attributes to achieve this.
- In our `MainActivity.java`, we must now set an onClickListener for the view `toggle_choices_visibility` so that the answer choices can hide on click and we can switch the icon we want to show
  - We can dynamically set the icon for an ImageView like so:

  ```java
  ((ImageView) findViewById(R.id.toggle_choices_visibility)).setImageResource(R.drawable.show_icon);
  ```

- Since we need to know whether to show or hide the answer choices and also which icon we should be displaying when the icon is clicked, we should keep a `boolean isShowingAnswers` in our MainActivity.java that gets toggled whenever the icon is clicked.
^^^

### Re-submitting Your Lab Project After Completing Optional Features

Anytime you complete more optional features for your app, you'll need to update your submission and re-submit.

1. Update your README by marking off any additional optional features you implemented, using the following syntax`-[x]`
1. Record a new GIF walkthrough that showcases the new features you implemented.
1. Add the GIF file to your repository and add the link in your README so it animates when the README is viewed.
1. Submit your app using the same **Submit** button found at the top of this lab page.

:::info
Checkout the **[Submitting Mobile Labs Guide](/courses/mobile_app_design/pages/submitting_coursework#heading-mobile-coding-lab-submissions)** for detailed instructions on submitting your lab. You can reference this **[Example README](https://gist.github.com/calren/1e2b05bb74cf9867a4212def64a810fc)** to see what a completed README should look like.
:::

## Concept Review

For a review of the topics we covered this week and addtional in-depth guides on these topics, feel free to browse the extra reading material [here](https://courses.codepath.org/courses/mobile_app_design/pages/android/links/unit_2.md)
