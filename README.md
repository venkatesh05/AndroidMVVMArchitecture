# AndroidMVVMArchitecture
Room + ViewModel + LiveData + RecyclerView (MVVM) - Android Architecture components and Migrated to Android Jetpack

This app using the Android Architecture Component libraries (Room, ViewModel, LiveData and LifeCycle), a RecyclerView and Java. The data will be stored in an SQLite database and supports insert, read, update and delete operations

We will set up a new Android Studio project, add the Room and Lifecycle dependencies and then create our Note class.
By annotating this Java class with @Entity, we can let room generate all the necessary code to create an SQLite table for this object, as well as columns for all it's fields. With @PrimaryKey and autoGenerate = true, we can turn an integer member variable into an autoincrementing primary key, which we can use to uniquely identify each row in the table

We will create our DAO and RoomDatabase.
The DAO is an interface that defines all the database operations we want to do on our entity. For this we declare methods without a method body and annotate them with @Insert, @Update, @Delete or the generic @Query, where we can pass an SQLite query

The Repository ist a simple Java class that abstracts the data layer from the rest of the app and mediates between different data sources, like a web service and a local cache. It hides the different database operations (like SQLite queries) and provides a clean API to the ViewModel. 

We will create our Viewmodel class.
The ViewModel works as a gateway between the UI controller and the repository. It stores and processes data for the activity/fragment and it doesn't get destoyed on configuration changes, so it doesn't lose it's variable state for example when the device is rotated

We will set up a RecyclerView to display the entries from our database table in our activity

