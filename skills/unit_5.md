## Lab 3 Topic Review

In the lab this week, we will explore the following:

- Adding libraries / dependencies through Gradle
- Persisting data in Android
- Using the Room persistence library

### Glossary of concepts introduced
Below is a list of concepts / terms that we will encounter in this week's lab, along with a short description and links for further reading if you're interested in learning more.

#### Gradle
Gradle is a dependency management system for Android. What this means is that we can use libraries that other developers created to make developing easier. For example, if we wanted our app to make a network call, we don't have to reinvent the wheel to implement it. Instead, we can pull in a networking library (by adding a dependency in Gradle) to make development faster.

[Read More about Gradle here](https://stackoverflow.com/questions/16754643/what-is-gradle-in-android-studio)  

#### SQL
SQL stands for Structured Query Language, and it's used to add, update, delete and retrieve information from databases. There are whole classes dedicated to understanding databases, but if you want to read about how it works and try out SQL queries, [this is a good place to start](https://www.w3schools.com/sql/sql_intro.asp)

#### Persistence in Android 
One of the most important parts of an app is being able to save data. Saving data means that our app will have the same information stored in it even if the user restarts the app, or restarts their phone. This can be done through a couple different ways: SharedPreferences, Text Files, and Databases. 

[Read More about Android Persistence here](https://guides.codepath.org/android/Persisting-Data-to-the-Device)

#### Room persistence library
Writing SQL queries for databases can be hard and complicated. So to make development easier, Google introduced a persistence library called Room. Room makes SQL queries easier to implement and use.

- [Read More about Room here](https://guides.codepath.org/android/Room-Guide)  
- [For comparison, this is how persistence through databases would be done without Room](https://guides.codepath.org/android/Local-Databases-with-SQLiteOpenHelper)  
- [Saving Data with Room (Includes helpful diagrams to explain the different files we created)](https://developer.android.com/training/data-storage/room/)

#### Empty States
A lot of times apps will have something called an 'empty state'. This is when the app doesn't have any data to display yet (perhaps when the user first launches it, or when the user gets to Inbox = 0 after cleaning out their emails in the Gmail app). 

[Check out some cool empty states concept here](https://dribbble.com/tags/empty_state)
