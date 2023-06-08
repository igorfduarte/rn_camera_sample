React Native Camera Sample Project
==================================

This repository hosts a **minimal React Native application** which utilizes the **react-native-camera** package to provide camera functionality. The project is built with **TypeScript**, and TypeScript definitions for react-native-camera have been installed.

Overview
--------

The heart of the application is the **CameraView** component, located within the **src** folder. This component interfaces with the **RNCamera** component from the react-native-camera package, and presents a simple user interface. A button on this interface triggers the photo capture functionality. This component is integrated into the main application via the **App.tsx** file.

Development Notes
-----------------

During the development process, a warning related to **PropTypes validation** was encountered. This warning, originating from the react-native-camera package, can be safely ignored.

### Android Configuration

For **Android configuration**, permissions required for camera usage were added to the **android/app/src/main/AndroidManifest.xml** file. The **android/app/build.gradle** file was also updated. A **missingDimensionStrategy** line was added under the defaultConfig block within the android section, to ensure correct operation of the react-native-camera package:
**missingDimensionStrategy 'react-native-camera', 'general'**

### TypeScript Configuration

The development process encountered an issue where the screen remained blank. This issue was traced back to the TypeScript configuration and the use of react-native-camera in a TypeScript environment. The solution was to utilize a **React.RefObject** for holding a reference to the RNCamera component, as demonstrated in the CameraView component's implementation.

The **PropsView error** is another aspect of the project to be aware of. This error doesn't affect the project's functioning and can be safely ignored. If preferred, it can be suppressed by modifying the TypeScript configuration.

Testing
-------

To evaluate the application, the **./gradlew build** command was utilized, and the resulting **app-release.apk** file was installed and tested on a mobile device. The app runs normally on the emulator as well. **npx react-native run-android** is sufficient for that.

Installation
------------

Please note that the provided project does not include the necessary packages. Thus, running the **npm install** command is essential to fetch all dependencies before initiating the application.
