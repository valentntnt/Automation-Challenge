# Automation-Challenge


Welcome to Rumah123 Automation Mobile Challenge, please follow below instruction for this chanllenge

## Requirement:
- use newest Appium Version
- use WebdriverIO as framework
- use CommonJS as a code
- use Page Object Model for code structure
- use Gherkin as Test Cases

## Test Cases:
- You are as an QA at 99, please download latest version of 99 (do not download the Pro Apps). You have the project to testing the revamp part on homepage, please scan all the locators and make it into the automation. so you can reduce testing time and also catch the bugs very sooner.
- How to access the homepage
1. please open the app
2. once it's open you will see the homepage


Rule:
- Please forking this repository
- Invite indra99co as collaborator
- once you done, please push into your branch and create the PR


## Setting Up

### 1. Environment Prerequisites
Make sure all of the following components are installed and properly configured:
* **Node.js** with project dependencies installed (`npm install`).
* **Android SDK** with `platform-tools` (`adb`) and properly configured environment variables (`ANDROID_HOME` / `PATH`).
* **Appium Server** with the **UiAutomator2** driver (and **Appium Inspector** if you need to inspect UI elements).
* **Physical Android device** connected via USB with **USB Debugging** enabled.

### 2. Verify Device Connection
Connect your Android device to your machine and verify that ADB detects it:

```bash
adb devices
```

Ensure your device ID appears with the status `device` (for example: `W8UG6HS4XOFYWWYP`).

### 3. Start Appium Server
Start Appium Server from your terminal:

```bash
appium
```

> **Note:** If you use **Appium Inspector** to scan element locators on the screen, close the active session in Appium Inspector before running the test suite so it does not conflict with the WebdriverIO session.

### 4. Capabilities & Project Configuration
Ensure the `capabilities` section in `wdio.conf.js` targets the native Android application (`com.urbanindo.android`) and activity `app.nine_nine.MainActivity` (rather than a Chrome browser session):

```javascript
capabilities: [
    {
        platformName: 'Android',
        'appium:automationName': 'UiAutomator2',
        'appium:deviceName': 'W8UG6HS4XOFYWWYP',
        'appium:appPackage': 'com.urbanindo.android',
        'appium:appActivity': 'app.nine_nine.MainActivity',
        'appium:noReset': true,
        'appium:skipDeviceInitialization': true,
        'appium:skipServerInstallation': true
    }
]
```

Also verify that `cucumberOpts.require` in `wdio.conf.js` points to your step definitions path (for example, `./features/step-definitions/**/*.js`).

### 5. Run the Test Suite
Open a terminal in the project root directory and run the tests:

```bash
npm run wdio
```

Or run directly using `npx`:

```bash
npx wdio run ./wdio.conf.js
```

### 6. Quick Troubleshooting Notes
* **`WRITE_SECURE_SETTINGS` / `hidden_api_policy`**: If a physical device blocks modifying global settings on session startup, verify that security debugging options in *Developer Options* are enabled and keep capabilities such as `noReset`, `skipDeviceInitialization`, and `skipServerInstallation` configured.
* **No Chromedriver found**: Make sure `capabilities` defines `appPackage` and `appActivity` instead of `browserName: 'Chrome'`.
* **Step "..." is not defined**: Check your step definition file paths and verify that `cucumberOpts.require` in `wdio.conf.js` matches them.

## Testing Documentation:
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/a26a77bb-afd1-4ee1-97f4-a9f6b0e8c604" />
