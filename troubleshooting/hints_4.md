### Common student questions: 

#### Where should I set an onClickListener when adding the "+" button?

Since the button you're adding is in `MainActivity`, the onClickListener should also be set in the `MainActivity`

#### My onClickListener() has errors when calling `startActivity()`

The example code was `StartingActivity.this.startActivity(intent)`. StartingActivity was an example, and this isn't the exact line of code we want. We should replace `StartingActivity` with `MainActivity`: `MainActivity.this.startActivity(intent)`

#### There are errors when I try to use EditText

Make sure you've imported the EditText class. You should have this line: `import android.widget.EditText`  at the top of your file with your other imports.

#### When I press the 'Save' button, I  don't see the question / card I just created

1. In order for data to be passed back from AddCardActivity to MainActivity, the `onClickListener()` for the Save button should include your Intent related code that contains the data for the Answer and the Question
2. Make sure you're calling `finish()` in AddCardActivity after the data has been set for the Intent.
3. In MainActivity, instead of calling `startActivity()`, you should now be calling `startActivityForResult(intent, 100)`. Calling `startActivityForResult()` tells MainActivity that it should be waiting for data to be passed back after AddActivity is closed.
