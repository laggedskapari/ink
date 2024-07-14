# Flutter, Bloc and Firebase Authentication: A seamless integration guide | by laggedskapari
You want to integrate **Firebase authentication** into your next awesome Flutter app using **Bloc**? Don't worry I'll help you figure how to do so or atleast I'll help you with basic implementation of it and you can modify it as you need.

For this article, I'll make a basic To-do app (yeah, Completely new idea who would've thought). It'll consist of :
- Sign Up page
- Sign In page
- Todo page

### Now Let's start with the coding fu*kery!

#### Step 0 : Setting up Firebase project and Flutter App
I mean you know how to so this right? 
- Create a new flutter app. *Guide* [here]()
- Setting up Firebase in Flutter app. *Guide* [here]()

#### Step 1 : Preparing repository and data models.
Let's start with creating a new directory called `packages` for declaring our data models and repositories.

Now we are going to create a new directory inside `packages` called `authentication` and define the `pubspec.yaml` file for it.

We need `cloud_firestore`, `equatable` and `firebase_auth` dependencies for our `packages/authentication` package.

[<script src="https://gist.github.com/laggedskapari/14302ede3cdf3bfdaa74287e8ffea9dc.js"></script>](https://gist.github.com/laggedskapari/a2f90e2d60ebf42d42e879c8d2bfe179)

Now all we have to do is, put our package into projects's `pubspec.yaml` file under dependencies section.

```yaml
# medium_todo_app/pubspec.yaml

dependencies:
  flutter:
    sdk: flutter


  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.8
  authentication:
    path: packages/authentication
```

and run the following command so it install all required dependecies.

```console
medium_todo_app$ flutter pub get
```
*Note: If this command does not generate `pubspec.lock` file for yout authentication package, then try to run it from inside of your authentication package.*
