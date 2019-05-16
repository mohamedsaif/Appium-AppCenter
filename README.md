# Appium-AppCenter

Simple iOS/Android Launch Test project to be used with App Center

## Generating Appium Templates using CLI

In order to generate the latest Appium code template, you can use [App Center CLI](https://github.com/microsoft/appcenter-cli).

Follow the instructions above to install the latest App Center CLI npm package.

```cmd
npm install -g appcenter-cli
```

Once installed, use the `appcenter` command.

> ***NOTE:*** This code was generated using App Center CLI version 1.1.18

Open you command line (or terminal) and move to a target folder and execute the following command:

In the android folder, execute the following command:

```cmd
appcenter test generate appium --platform android --output-path .
```

In the iOS folder, execute the following command:

```cmd
appcenter test generate appium --platform ios --output-path .
```