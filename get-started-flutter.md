# Flutter Development Environment Setup on Windows

## Table of Contents

- [System Requirements](#system-requirements)
- [Install Git for Windows](#install-git-for-windows)
- [Download Flutter SDK](#download-flutter-sdk)
- [Verify Installation](#verify-installation)
- [Install Android Studio](#install-android-studio)
- [Set Up the Android Emulator](#set-up-the-android-emulator)
- [Set Up Visual Studio Code (Optional)](#set-up-visual-studio-code-optional)
- [Run Your First Flutter App](#run-your-first-flutter-app)
- [Keeping Flutter and Tools Up to Date](#keeping-flutter-and-tools-up-to-date)
- [Conclusion](#conclusion)

## System Requirements

Ensure your system meets the following minimum requirements:

- **Operating System**: Windows 10 (64-bit) or later.
- **Disk Space**: At least 1.64 GB (does not include disk space for IDE/tools).
- **Tools**: Windows PowerShell 5.0 or newer and Git for Windows.

## Install Git for Windows

1. **Download Git**: Visit [Git for Windows](https://git-scm.com/) and download the latest version.
2. **Install Git**: Run the installer and follow the setup instructions. Make sure to select the option “Use Git from the Windows Command Prompt” during the installation.

## Download Flutter SDK

1. **Download Flutter SDK**: Go to the [Flutter official website](https://flutter.dev/docs/get-started/install/windows) and download the latest stable release of the Flutter SDK.
2. **Extract Flutter SDK**:
   - Right-click the downloaded ZIP file and select “Extract All…”.
   - Choose the location where you want to store the SDK (e.g., `C:\src\flutter`).
3. **Update Path**:
   - Open **Start Menu**, search for **Environment Variables**, and select **Edit the system environment variables**.
   - In the **System Properties** window, click **Environment Variables**.
   - Under **System variables**, find and select the `Path` variable, then click **Edit**.
   - Click **New** and add the path to the `flutter\bin` directory (e.g., `C:\src\flutter\bin`).
   - Click **OK** to close all dialogs.

## Verify Installation

1. **Open PowerShell**: Open PowerShell or Command Prompt and run the following command to verify the installation:

   ```bash
   flutter doctor
   ```

2. **Check Output**: The command checks your environment and displays a report of the status of your installation. You may need to install additional dependencies if any issues are reported.

   - Unable to locate Android SDK:

      ```bash
      flutter config --android-sdk <PATH_TO_ANDROID_SDK>
      ```

      ![alt text](./img/Screenshot%202024-09-04%20115737.png "image")

   - Androin toolchain:

      ![alt text](./img/Screenshot%202024-09-04%20120054.png "image")

      - cmdline-tools component is missing: make sure Android SDK Command-line is checked and installed in Android Studio > SDK Manager > SDK Tools.

      ![alt text](./img/Screenshot%202024-09-04%20151556.png "image")

      - Android license status unknown: run following command and press y then Enter to confirm licenses.

      ```bash
      flutter doctor --android-licences
      ```

## Install Android Studio

1. Download Android Studio: Visit the [Android Studio download page](https://developer.android.com/studio) and download the installer.

2. Install Android Studio:

   - Run the installer and follow the setup instructions.
   - During installation, ensure that the boxes for Android SDK, Android SDK Platform, Android Virtual Device are checked.

      ![alt text](./img/Screenshot%202024-09-04%20105452.png "image")

   - Set the Android SDK path during the installation process. It’s usually set in C:\Users\<Your-Username>\AppData\Local\Android\Sdk.

3. Install Flutter and Dart Plugins:

   - Open Android Studio.
   - Go to File > Settings.
   - Under Plugins, search for "Flutter" and install it.
   - When prompted, also install the Dart plugin.

## Set Up the Android Emulator

1. Open Android Studio.
2. Virtual Device Manager: More Actions > Virtual Device Manager.

   ![alt text](./img/Screenshot%202024-09-04%20152832.png "image")

3. Create a Virtual Device: Click Create Virtual Device, select a device model, then click Next.

   ![alt text](./img/Screenshot%202024-09-04%20151722.png "image")
   ![alt text](./img/Screenshot%202024-09-04%20152604.png "image")

4. Select a System Image: Choose a system image that matches the version you want to test, and click Next.

   ![alt text](./img/Screenshot%202024-09-04%20152610.png "image")

5. Verify Configuration: Confirm the configuration settings and click Finish.

   ![alt text](./img/Screenshot%202024-09-04%20152616.png "image")

## Step 7: Set Up Visual Studio Code (Optional)

1. Install VS Code: Download and install Visual Studio Code.
2. Install Flutter Extension:
   - Open VS Code.
   - Go to Extensions.
   - Search for "Flutter" and install the official Flutter extension. This will also install the Dart extension.

   ![alt text](./img/Screenshot%202024-09-04%20150605.png "image")

## Run Your First Flutter App

1. Create a New Flutter Project:
   - Open PowerShell or Command Prompt.
   - Navigate to the directory where you want to create your Flutter project.
   - Run the following command:

      ```bash
      flutter create my_first_app
      ```

   - Navigate into your project directory:

      ```bash
      cd my_first_app
      ```

2. Run the App:

   - Ensure your Android emulator is running or a physical device is connected.

      ![alt text](./img/Screenshot%202024-09-04%20153413.png "image")

   - Run the following command to launch your app:

      ```bash
      flutter run
      ```

## Keeping Flutter and Tools Up to Date

1. Update Flutter SDK:

   - To update the Flutter SDK, run:

      ```bash
      flutter upgrade
      ```

2. Update Android Studio:
   - Check for updates regularly within Android Studio to ensure you’re using the latest version of the Android SDK and related tools.
