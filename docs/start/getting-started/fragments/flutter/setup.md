
👋 Welcome! In this tutorial, you will:

- Setup your Flutter development environment 
- Add the Amplify Flutter Library dependencies
- Create a basic app that records an analytics event
- Use Amplify CLI to setup your AWS backend resources 

## Prerequisites

- [Install Flutter](https://flutter.dev/docs/get-started/install) version 1.20.0 or higher (make sure you are using a stable version of flutter)

- [Setup your IDE](https://flutter.dev/docs/get-started/editor?tab=androidstudio)

    This tutorial assumes you are using AndroidStudio to develop your app. 

- Install the [Amplify CLI](~/cli/cli.md) by running:

    <inline-fragment src="~/fragments/cli-install-block.md"></inline-fragment>

- Sign up for an AWS account

    If you don't already have an AWS account, you'll need to create one in order to follow the steps outlined in this tutorial.

    [Create AWS Account](https://portal.aws.amazon.com/billing/signup?redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start)

    > There are no upfront charges or any term commitments to create an AWS account and signing up gives you immediate access to the AWS Free Tier.


## Set up your application

### Create a new Flutter application 

1. Create a new project using Flutter CLI:

    ```bash
    flutter create todo
    ```

2. Or using **Android Studio**. Select **+ Start a new Flutter project**.

    ![](~/images/lib/getting-started/flutter/set-up-android-studio-welcome.png)

3. In **Select a Project Template**, select **Flutter Application**. Press **Next**.

    ![](~/images/lib/getting-started/flutter/set-up-android-studio-select-project-template.png)


Next, configure your project:

    - Enter *todo* in the **Name** field
    - Make sure your Flutter SDK path is set correctly to where it is installed on your machine 
    - Press **Next**.  On the next screen, press **Finish**. 

  ![](~/images/lib/getting-started/flutter/set-up-android-studio-configure-your-project.png)

Android Studio will open your project with a tab opened to *main.dart*

1. Modify your Podfile to target iOS platform 11.0 or higher.  Within your project open `ios/Podfile` and change the second line to be `platform :ios, '11.0'. 
2. Modify your AndroidManifest.xml to target minSDK 21 or higher.  Within your project open `android/app/src/main/AndroidManifest.xml` and change the line starting with `minSdkVersion` to be `minSdkVersion 21`. 

You now have an empty Flutter project into which you’ll add Amplify in the next steps.

### Add Amplify to your application

Amplify for Flutter is distributed via **pub.dev**.


1. Open your **app**'s `pubspec.yaml` and add the following 3 dependencies below the line "sdk:flutter". 

```yaml
dependencies:
  flutter:
    sdk: flutter

  amplify_flutter: '<1.0.0'
  amplify_auth_cognito: '<1.0.0'
  amplify_analytics_pinpoint: '<1.0.0'
```

2. Run **Flutter Pub Get**

    Android Studio requires you to sync your project with your new configuration. To do this, you can click **Flutter** in the notification bar above the file editor.  

    ![](~/images/lib/getting-started/flutter/set-up-android-studio-pub-get.png)

    Alternatively, you can open a terminal window, cd into your project's root directory (where your pubspec.yaml is) and run: 

    ```bash
    flutter pub get 
    ```

    When complete, you will see *Process finished with exit code 0* in the output of the *Messages* tab at the bottom of your screen.
    
    ![](~/images/lib/getting-started/flutter/set-up-android-studio-configure-successful.png)
    
You are ready to start building with Amplify! 🎉
