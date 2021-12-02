## Lab 1 Topic Review

In the lab this week, we will explore the following:

- Create a new app project
- Add different UI views on a screen
- Customizing UI
- Understand how to debug crashes and log useful messages
- Push project to Github

### Glossary of concepts introduced
Below is a list of concepts / terms that we will encounter in this week's lab, along with a short description and links for further reading if you're interested in learning more.

#### minSdk version
Specifies the minimum version of the Android Operating System required to run your application. For example, if your application's minSdk was set to 26, then Android phones running any Android version below 26 would not be able to install your app.  

[Read more about supporting different platforms versions for Android apps](https://developer.android.com/training/basics/supporting-devices/platforms)

#### Activity
All Android Apps contain at least one Activity and often multiple Activities. An Activity is a screen/window in your app that users can interact with.  

[Introduction to Android's Activities](https://developer.android.com/guide/components/activities/intro-activities)

#### XML
XML is a type of markup language similar to HTML. Specifically for Android, UI layouts are implemented with XML files  

[More about Writing XML for Android Layouts](https://developer.android.com/guide/topics/ui/declaring-layout#write)

#### RelativeLayout and ConstraintLayout
All layouts in Android must have a type of root layout type, and the most common ones are RelativeLayout, LinearLayout, and ConstraintLayout. RelativeLayout is useful for when elements need to be positioned relative to other elements in the layout.
ConstraintLayout can be thought of as a more advanced and flexible type of RelativeLayout that is more useful for more complicated layouts.  

[More reading on different types of Android Layouts](https://guides.codepath.org/android/Constructing-View-Layouts)

#### View 
Views in android are contents that are drawn onto the screen of an Android device. It can be anything from a Button, TextView, ImageView, or even the root layout that holds all the views. They are usually created in XML layout files. 

#### TextView
TextViews are a specific type of view in Android that is used to display text. It allows for many customizations such as font, font size, font color, and more.  

[Read more about Working with TextViews in Android](https://guides.codepath.org/android/Working-with-the-TextView)

#### id
id values are used in Android's xml layout files to identify views. When the plus symbol, +, is used, it indicates that this is a new id. For example `android:id="@+id/name"` tells Android to create a new resource id for this view. When the id is not used with a "+" it means we're referencing it. For example `android:layout_below="@id/top_view"` is referencing a separate view labeled with the id `top_view`  

If a view is idenfitied in the xml file as `android:id=@+id/my_button`, we can later access it in our Java code like so: `View myButton = findViewById(R.id.my_button)`

#### dp / sp
`dp` and `sp` are units of measurement. Since Android devices come in many different screen sizes that each have their own pixel sizes (for example one device can have 160 pixels per square inch, while another device fits 480 pixels in the same space) , using `sp` and `dp` helps UI look consistent across all devices.

`dp` stands for density pixels and should be used for views' height, width, margin, and padding. `sp` stands for scale pixels and should be used for font sizes since it can be affected based on the user's setting for font display on their phone.

[Read more about Supporting Different Screen Sizes on Android](https://developer.android.com/training/multiscreen/screendensities)
[Understanding Pixel Density](https://material.io/design/layout/understanding-layout.html#pixel-density)

#### match_parent
`match_parent` is a specific type of LayoutParam that lets the view tell its parent how it wants to be laid out. For example, if a view's width is set to `match_parent`, that means the view wants its width to be as big as its parents view.

In the example below, `parent_view` has a width of `match_parent` which means it's width will take up as much space as the Android phone's screen. `child_view`'s height is set to `match_parent`, which means it will be `300dp` because that's what it's set to for `parent_view`

```xml
<View
  android:id="@+id/parent_view"
  android:layout_width="match_parent"
  android:layout_height="300dp">

  <View
    android:id="@+id/child_view"
    android:layout_width="200dp"
    android:layout_height="match_parent" />
</View>
```

[Read more about Android Views LayoutParams](https://developer.android.com/reference/android/view/ViewGroup.LayoutParams)

#### Listener
Listeners are objects that can be attached to views in order to react to input events from the user.

For example, we can print out text when a button is clicked with the following code

```java
Button btnExample = (Button) findViewById(R.id.btnExample);
btnExample.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        System.out.println("Clicked!")
    }
});
```

[More info about Basic Event Listeners](https://guides.codepath.org/android/Basic-Event-Listeners)

#### Github
Github is a tool for tracking and storing changes for our code. It gives us a way to ensure that we always have a working copy of our project and allows us to push our updates online so that they won't be lost if the code on our computer got deleted.  

[GitHub Guide](https://courses.codepath.org/courses/mobile_app_design/pages/android/github_how_to.md)
[Github Introduction Walkthrough](https://guides.github.com/activities/hello-world/)
