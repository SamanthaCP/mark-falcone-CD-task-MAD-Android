## Lab 2 Topic Review

In the lab this week, we will explore the following:

- Android Intents
- Creating Navigation Flows
- Passing data around different Activities
- Giving user feedback on their actions
- Passing data to other apps outside of our own

### Glossary of concepts introduced
Below is a list of concepts / terms that we will encounter in this week's lab, along with a short description and links for further reading if you're interested in learning more.

#### Intents
An Intent is Android's way of saying it has an "intention" to perform an action. Android uses these Intent objects to specify what it wants to happen (ie : start a new Activity). When an Intent is used, data can also be attached to the Intent so that more information can be given to the 'receiver' of the intent.  

[Read More about Android Intents here](https://guides.codepath.org/android/Using-Intents-to-Create-Flows)

#### Resources and Drawables  
Resources in Android can be used to define a wide range of things (colors, images, layouts). Drawables are a specific type of resource. Drawables can be Bitmap files or XML files that we can use as icons or backgrounds for views.

[More about Android Resources](https://guides.codepath.org/android/Understanding-App-Resources)
[More about Drawables](https://guides.codepath.org/android/drawables)

#### SVG vs PNG
SVG and PNG are different types of image file formats. SVG is nice in that it's in vector format, so it can scale to different sizes without looking blurry. This is nice for Android development because it helps accomodate all the different sizes of Android screens.

#### Android's Activity Lifecycle
Every Activity in Android goes through something called a Lifecycle. When an Activity is first shown, it is in the `onCreate` phase. When an Activity is dismissed explicitly, it goes into the `onDestroy` phase. We can explicity dismiss an activity by calling `finish()`. The `finish()` method dismisses the activity which leads it to the `onDestroy` phase. There are many other phases in between those two, but those are often the most important ones.

[More about Android Activity Lifecycle](https://guides.codepath.org/android/Activity-Lifecycle)

#### EditText View
EditText is a specific type of view that allows user input. It can be customized in many different ways including but not limited to: how many lines of text the user can input, what is shown when there is no input yet, the text color, ....

[More about working with EditText Views](https://guides.codepath.org/android/Working-with-the-EditText)

#### Toasts
A toast is a small popup message that automatically goes away after a specified amount of time.  

<img src="http://developer.android.com/images/toast.png" width="300"/>  

[More about working with Toasts](https://guides.codepath.org/android/Displaying-Toasts)

#### Snackbar
A Snackbar is similar to a Toast in that it shows a fleeting message. It's advantage over Toasts is that it's more customizable in that we're able to style it in certain ways and add click listeners to it.

<img src="https://i.imgur.com/opY0OvG.png" width="300"/>  

[More about working with Snackbar](https://guides.codepath.org/android/Displaying-the-Snackbar)

#### Implicit vs Explicit Intents
Explicit intents are intents where we know exactly what we want to do (ie : start a certain activity within our app). Implicit intents are intents where we simply have a certain action we want to perform (ie : start a phone call or open a maps app). Implicit intents can be used to start other apps on a user's phone to complete an action like sending a message. This is how when you press the 'Share' button in some apps, you get a variety of choices of how you want to share your content.

[More about Intents](https://guides.codepath.org/android/Using-Intents-to-Create-Flows)
[Common Implicit Intents](https://guides.codepath.org/android/Sharing-Content-with-Intents)
