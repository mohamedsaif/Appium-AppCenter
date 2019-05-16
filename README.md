# Appium-AppCenter

Simple iOS/Android Launch Test project to be used with App Center

## Clone the repo

You can clone this repo to your [Azure DevOps Repos](https://devops.azure.com), GitHub or any preferred git repo that you usually use.

If you want to create your own code, please follow the steps below to use the App Center CLI to do just that :)

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

## Updating your tests

If you want to run the test locally, you can update the following setup method with the right parameters:

```java
@Before
public void setUp() throws MalformedURLException {
    DesiredCapabilities capabilities = new DesiredCapabilities();

    //Note that only on a Mac you can run Appium tests locally
    capabilities.setCapability("platformName", "iOS");

    //Replace the device name here with your connected physical device or simulator name
    capabilities.setCapability("deviceName", "iPhone 6");

    //Update the path here to the absolute location of the application package (incase of iOS, or apk incase of android)
    capabilities.setCapability("app", "/path/to/app.app");

    //Please note that you might need additional configuration to be passed on as well (like in Android you need the appWaitActivity incase your app has multiple startup activities)
    //capabilities.setCapability("app", "C:\\Biz\\Repos\\ContosoShopManager.App.Tests\\android\\com.contoso.shopmanager.apk");
    //capabilities.setCapability("appWaitActivity", "md5fc8352c09fc0e94a1fb6865a21611090.MainActivity");

    URL url = new URL("http://localhost:4723/wd/hub");

    driver = Factory.createIOSDriver(url, capabilities);
}
```