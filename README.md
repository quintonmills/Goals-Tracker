# React Native E2E Testing with Detox

Learn how to setup your local or CI environment to run E2E tests on iOS & Android emulators with Detox. Write E2E tests for a demo application covering best practices and gotchas along the way.

## Table of contents
- [Start Project](#start-project)
- [Running](#running)
- [App Overview](#app-overview)
- [E2E Test Cases](#e2e-test-cases)

# Start Project

## Prerequisites

In case you've never developed React Native apps before - you'll need to install Android and iOS development environment. Open link below, select **React Native CLI** tab and install everything needed for iOS and Android.

- 📚 [React Native Environment Setup Guide](https://reactnative.dev/docs/next/environment-setup)


Note: we will **node version 14** for this project.

## Clone this project

Most likely you've done it already, but just to be sure😄

- 🔗 [Repository link](https://github.com/quintonmills/goals-tracker)


## Install Detox Command Line Tools

```sh
npm install -g detox-cli
```
## Install applesimutils (iOS only)

A collection of utils for Apple simulators, Detox uses it to query and communicate with the simulator.

```sh
brew tap wix/brew
brew install applesimutils
```

## Install dependencies

```sh
// Install dependencies
npm install

// Install pods
cd ios && pod install
```
## Start project

```sh
// Start Metro in new terminal
npx react-native start

// Starting iOS (should launch simulator automatically)
npx react-native run-ios

// Launch Android emulator (note: it is better to use AOSP emulators)
emulator -list-avds

emulator @emulatorNameFromPrevious

// Starting Android
npx react-native run-android
```

If everything went well - you will see app with movies running in iOS and Android simulators.

# Running

## Run tests to make sure the configuration is correct

```sh
detox build -c <configuration name>

npx react-native start

detox test -c <configuration name>
```

# App Overview

We love tracking our goals! The demo is an app for our detox demonstration.

There is only one main screen

![This is an image](https://github.com/quintonmills/Goals-Tracker/blob/master/assets/goalstracker.png)


The main tab is a list of Goals. You can also add Goals in the tracker by filling out the text box at the top of the screen.

# E2E Test Cases 

We want to write e2e tests to cover these user flows
- [ ] user can create own goal and add it
- [ ] user can view all added goals
