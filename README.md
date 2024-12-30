# Expo Linking.getInitialURL() Intermittent Null Return

This repository demonstrates an uncommon bug encountered when using the Expo `Linking` API. The `getInitialURL()` method sometimes returns `null` even when the app is launched with a deep link. This behavior appears to be intermittent and difficult to reproduce reliably.

## Bug Description

The primary issue lies with the inconsistency of `Linking.getInitialURL()`.  In some instances, particularly when the app is launched while offline or when there's a latency in receiving the deep link, the function returns `null`. This results in unexpected behavior in the app's deep linking functionality.

## Reproduction Steps

The exact reproduction steps are difficult to pinpoint due to the intermittent nature of the bug.  However, it's more likely to occur under conditions of low network connectivity or when there's a significant delay between launching the app and receiving the deep link data.

## Solution

The suggested solution involves implementing error handling and potentially retrying the `getInitialURL()` call after a short delay, to mitigate the issue of intermittent null returns.  This repository offers a modified implementation using `AsyncStorage` to potentially store and retrieve the deep link URL, allowing you to attempt recovery.

## Additional Notes

This bug report should help users to understand how to address the intermittent null return issue from `Linking.getInitialURL()` in Expo apps. This will help to ensure a more robust and reliable deep link handling experience.