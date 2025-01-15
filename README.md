# Expo Camera Preview Bug

This repository demonstrates a bug encountered when using the Expo Camera API in conjunction with React Navigation.  The issue manifests as a failure of the camera preview to render correctly after navigating away from and then returning to the screen containing the camera.  The camera functions correctly in terms of taking pictures, but the preview is broken.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app on an iOS or Android device or simulator.
4. Navigate to the screen containing the camera.
5. Navigate to another screen.
6. Navigate back to the screen with the camera.

You should observe that the camera preview fails to render correctly.

## Solution

The solution involves using the `onMount` hook from the `react-native-reanimated` library to ensure the camera is properly initialized and mounted before rendering the preview. This forces a remount of the camera when the component is re-rendered after navigation.  Please see `bugSolution.js` for the corrected code.