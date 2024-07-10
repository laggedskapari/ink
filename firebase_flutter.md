# Firebase with Flutter and Bloc - The correct way

This is more like a beginners guide for how to use firebase with flutter and bloc. I don't know what your use cases will be, but I'll give you guys
a idea of some fundamentals so you can build upon that, In order explain you clearly I'll take example of a basic To-do app.

Area that we are going cover :
- **Creating Firebase project**
- **Creating a Flutter app.**
- **Installing the required Firebase CLI tools.**
- **Configuring app to use Firebase in our To-do app.**


Enough talk, Now let's dive into the coding fu*kery.

## 0. New Firebase project
## 0. Let's create a new flutter project.

You know how to do that, right? `flutter create <YOUR_PROJECT_NAME>` remember?.

```
flutter create MEDIUM_TODO_APP
```

## 1. Intalling the required command line tools

1. First make sure that you have **Firebase CLI** installed. If you don't your terminal or check the official doc [here](https://firebase.google.com/docs/cli)
2. After installing firebase cli, we going to authenticate it using 
```console
$ firebase login
```
3. Now we are successfully authenticated and going are to install install the Flutterfire CLI by running 

```console
$ dart pub global activate flutterfire_cli
```

**Note: Above command can be ran from any directory.**
## 2. Configuring app to use Firebase
Finally, We can use FlutterFire CLI to configure your Flutter apps to connect to Firebase.
In order to do so, we run the following command from our `flutter project directory`.
```console
MEDIUM_TODO_APP$ flutterfire configure
```
**Understanding what `flutterfire configure` does :** 
1. Asks you to select platform support in your flutter app (iOS, Android, Web).
2. Let you select or create **Firebase** project for your Flutter app.
3. Creates a Firebase configration file `firebase.json` and add it to you `lib/` directory.

To read about it more, Please refer to  **Firebase** docs [here](https://firebase.google.com/docs/flutter/setup).

## 4. Initializing Firebase in our app
1. Make sure that you are in your Flutter project directory.

2. We are going to install the `firebase_core` plugin in our app.
```console
MEDIUM_TODO_APP$ flutter pub add firebase_core
```

3. We are going to re-run the `flutterfire configure` command to ensure that our Firebase configration is up-to-date.
```console
MEDIUM_TODO_APP$ flutterfire configure 
```
4. Now, let's import the `firebase_core` plugin and the `firebase_options.dart` file that were generated earlier into our `lib/main.dart` file.
```dart
//main.dart
import 'package:firebase_core/firebase_core.dart';
import 'firebase_options.dart';
```
5. In our `lib/main.dart` file, we'll now initialize Firebase using the `DefaultFirebaseOptions` object exported by the configration file.
```dart
//main.dart
await Firebase.initializeApp(
  options: DefaultFirebaseOptions.currentPlatform,
);
```

