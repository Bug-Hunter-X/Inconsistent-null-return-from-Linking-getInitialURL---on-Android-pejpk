# Expo Linking.getInitialURL() Inconsistent null return on Android

This repository demonstrates a bug encountered when using Expo's `Linking.getInitialURL()` API on Android.  The method inconsistently returns `null`, even when the app is launched via a deep link.

The problem is intermittent and challenging to reproduce reliably, making debugging difficult.  The provided solution offers a workaround to mitigate the issue.

## Reproducing the Bug

Follow these steps to potentially observe the bug:
1. Clone this repository.
2. Run the project on an Android device or emulator.
3. Attempt to launch the application via a deep link (the specific link is included in the code).
4. Observe the console output; it will either display the deep link URL or `null`.

## Solution

The provided solution introduces a timeout mechanism using `setTimeout`.  This allows time for the `Linking.getInitialURL()` API to resolve before proceeding.   While this doesn't fix the root cause of the problem, it provides a reliable way to handle the intermittent `null` returns.

## Additional Notes

This issue may be related to Android's background processes handling or the timing of the `Linking` API.