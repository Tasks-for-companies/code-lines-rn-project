### React Native Project for CODELINES Ltd

The exercise is about creating a React Native app (with or without the use of
Expo) that will perform the 2 main following functionalities:

- Login user with the help of Firebase authentication (email, password)
- Chat functionality that allows users to perform comments over a list of
  movies

#### Part 1: User authentication

1. Create a view where the new users can register by providing their email /
   password the first time they open the app.
2. On app reopen user should be considered logged in and the app should
   not show this view again.
3. Create a firebase app and use authentication APIs through there.
4. It’s not important how the UI will look like exactly but make it presentable

#### Part 2: Movies list

5. Create a list that will retrieve movies from the sample provided json file
   and for each movie will show only its title and some click indication, like an
   arrow button at the end of the line.
6. On click open of each list line, a new chat screen will appear where 2 or
   more users will be able to type their comments. Comments should be
   displayed and also persisted.
7. Data persistence should take place in Real Time Database of the Firebase
   app you created already.
8. UI again is not important. Just make it presentable.
   Notes:
   Make sure to create a README.md file in the project where you will list:
9. File structure that you worked with
10. Project implementation details and some decisions you took
11. If you had more time what would you improve

=================================================================\
Notes:

- Time to finish: 14 hours over 4 days (weekend included).
- Tested on iPhone 11.
- Has 2 branches. Thes second `FlatlistMovies` should be deleted.

=================================================================

#### 1. File Structure:

The app consists of the following folders:

- assets
- components
- constants
- screens
- styles
- utils

#### 2. Project implementation details - decisions:

- For a reall app I would have used, `React Navigation`, but here I just render screens according to state variables.
- In order to hide/show the `AuthScreen` and the `Logout` button, I pass a function (namely `checkUserState`) from the child `AuthScreen` to the parent `App`, which checks if `userData` is stored in device, and acts accordingly. Normally I would have used `redux`. Further more I do the same to hied/show `ChatScreen` using the `chatHandler` function.
- When user navigates to a chat screen, by clicking the name of a movie, the name of the movie, is shown on the chat screen.
- Check movies: `Prometheus` and `Suicide Squad` for comments.

#### 3. Things that could be improved:

- The token from firebase expires after 1 hour, I could use the `refreshToken` to ask for a new one and keep the user logged in.
- [Solved] Load first 10 movies and then per scroll load extra 10 movies, unitll the end of the list.
- Save the movies list in firebase and fetch it.
- Add email and password validation.
- Disable login/singup button while user has not filled in email and password.
- Add `ActivityIndicator` when pressing a button.
- Add icon to logout.
- Add ability to send photos in chat.
- Add number of users that participate in the chat room.
- Add user name and profile picture to comments.
- Add rules to firebase and use a token to save messages.
- Add try/catch blocks and show error messages.
- [Solved] Use a more user friendly date to comments.
- [Solved] Use a ScrollView to render all the comments and per scroll load more...
- [Solved] I have `comment` as a dependency in useEffect that fetches the comments, in order to show the comment when user sends it. That makes useEffect run an every letter the user types. Should only run when user sends the comment.

Thank you!
