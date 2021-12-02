Be sure to review the following issues if you are running into problems with this lab:

#### Issue with your emulator or Android Studio?

  Check out the [Android Troubleshooting Guide on Emulators](https://hackmd.io/@nesquena/r1bhe4La7?type=view#Something-weird-is-happening-with-my-emulator-or-Android-Studio).

#### Fixing Layout Preview Not Showing

 If you are not able to see a preview of your layout and see an error that says 'Render problem. Failed to load AppCompat ActionBar with unknown error:
 1) Open up the file `/res/values/styles.xml` . You can open this file with Cmd + Shift + N and type in 'styles' (Cmd + Shift + O on Mac)
 2) look for the line that says `<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">` and change it to `<style name="AppTheme" parent="Base.Theme.AppCompat.Light.DarkActionBar">`

#### OnClickListener does not work

  Are you setting the onClickListener at the right place? (In the `onCreate` method and after `setContentView(R.layout.activity_main);`)

#### Help! My application won't open. Or it says "\<App Name\> keeps stopping"

  Check out the [Android Troubleshooting Guide on debugging crashing applications](https://hackmd.io/@nesquena/r1bhe4La7?type=view#My-app-is-crashing-with-a-dialog-and-then-exits)

#### Why does is my `android:text` xml code highlighted in yellow?

  If you're seeing that Android Studio is highlighting your strings and giving the error "Hardcoded string, should use @string resource". That's because it's best practices when writing android code to put your strings into a separate file rather than hard coding the string values themselves. You can do this by using the quick fix shortcut `Option+Enter` on Mac `Alt+Enter` on Windows, and select `Extract as String resource`. This will put the strings into `res/values/strings.xml` where you can see all the strings. See [this guide on string resources](https://guides.codepath.org/android/Understanding-App-Resources#defining-a-string-resource) for more information.
