### Common Questions

### Where should I place the overridePendingTransition code?

- Notice that you should already have code to start the AddCardActivity. You should place the `overridePendingTransition()` related code right after you call `startActivity(intent)`

### How do I implement the animation to reveal an answer if I've already implemented the multiple choice option?

- One option is to let user have both the option to 'reveal' the answer by tapping on the card and also the option to choose a multiple choice answer. This also leads to a great user experience as now the user can chose to 'reveal' and answer if they're not sure which multiple choice answer is correct. 

### After implementing the 'card flip' animation, the card only displays the answer instead of the question when the 'Next' button is tapped

- When the 'next' button is tapped, be sure to also handle resetting the `yRotation` of the card (the `yRotation` should be `0` if you want to show the Question and `90` if you want to show the Answer).

### My app is crashing when I press the 'Next' button

- This might be happening because there are no more available cards in your database. One way to avoid crashing the app is to specifically check if there are more cards available when the 'Next' button is clicked. You chould show a [Snackbar message](https://guides.codepath.com/android/Displaying-the-Snackbar) to inform the user that there is no available card to display next.
