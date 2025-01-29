# React Native Dimensions API returns undefined/0 on Android

This repository demonstrates a common bug in React Native where the `Dimensions` API returns `undefined` or `0` for width and height, particularly on Android during app launch or orientation changes.  The example showcases the problem and provides a solution using `Dimensions.addEventListener` to listen for dimension changes.

## Problem
The `Dimensions.get('window')` method might return incorrect dimensions immediately after app launch or orientation changes.  This leads to layout issues or crashes if the app relies on these values for layout calculations before they are accurately determined.

## Solution
The solution involves using `Dimensions.addEventListener` to listen for changes in screen dimensions.  The component will update its layout once the dimensions are available and reliable.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run the app on an Android emulator or device.
4. Observe the initial layout and how it updates after a short delay or an orientation change.

## Additional notes:
This bug is more prevalent on Android due to variations in how the operating system provides screen dimension information.
