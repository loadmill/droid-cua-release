# droid-cua

<p align="center">
  <a href="https://www.npmjs.com/package/@loadmill/droid-cua"><img src="https://img.shields.io/npm/v/@loadmill/droid-cua?color=green" alt="npm version"></a>
</p>

<p align="center">
  <a href="#what-is-droid-cua">What is droid-cua?</a> •
  <a href="#quick-start">Quick Start</a> •
  <a href="#platforms">Platforms</a> •
  <a href="#features">Features</a> •
  <a href="#how-it-works">How It Works</a> •
  <a href="#cli-and-automation">CLI & Automation</a> •
  <a href="#release-artifacts">Release Artifacts</a> •
  <a href="#license">License</a>
</p>

---

**AI-powered mobile testing desktop app for Android and iOS**

Create, run, and manage mobile tests with natural language. The desktop app guides setup, connects to your target device or simulator, and turns AI exploration into reusable test scripts.

This repository is the public release-artifacts repository for `droid-cua`.
It is used for desktop app downloads and release notes.

---

<h2 id="what-is-droid-cua">What is droid-cua?</h2>

`droid-cua` is a desktop app and CLI for AI-powered mobile testing.

It helps teams create, edit, and run tests for **Android devices and emulators** and **iOS simulators on macOS** using natural language instead of traditional test code.

Under the hood, `droid-cua` uses an AI agent to explore your app, execute actions, and save reusable test scripts that can also be run later in headless workflows.

---

<h2 id="quick-start">Quick Start</h2>

**1. Download the desktop app**

Get the latest stable desktop build from [GitHub Releases](https://github.com/loadmill/droid-cua-release/releases).

**2. Launch the app**

Open the desktop app and choose the platform you want to test.

**3. Add your credentials**

Set your OpenAI API key in the app Settings screen, or log in with your Loadmill account.

**4. Connect a target device**

- Android: connect a device or select an emulator
- iOS: choose a simulator on macOS

**5. Create or run a test**

Use the desktop app to create a new test, edit an existing one, or run a saved script with live execution logs.

You can also keep project run history in a results folder and review past runs from desktop app reports.

---

<h2 id="platforms">Platforms</h2>

- **Android** - Physical devices and emulators
- **iOS** - Simulators on macOS

## Requirements

**All platforms:**
- OpenAI API key

**Android:**
- Android Debug Bridge (ADB)
- Android Emulator CLI for launchable emulators

**iOS (macOS only):**
- Xcode with iOS Simulator
- Appium
- XCUITest driver

---

<h2 id="features">Features</h2>

- **Desktop-first workflow** - Create, run, and manage tests from one app
- **Setup guidance** - Configure API access and platform prerequisites in the app
- **Device and simulator connection** - Connect Android targets and iOS simulators
- **Natural-language test creation** - Describe flows in plain English
- **Test management** - Create, edit, save, and rerun reusable scripts
- **Live execution logs** - Watch actions and progress as tests run
- **Reports and history** - Review past runs from a project results folder inside the desktop app
- **JUnit XML output** - Write standard test reports for CI systems and external tooling
- **Headless support** - Reuse scripts in CLI and automation workflows

---

<h2 id="how-it-works">How It Works</h2>

1. The desktop app connects to an Android device or emulator through ADB, or to an iOS simulator through Appium + XCUITest
2. Captures full-screen device screenshots
3. Scales down the screenshots for model compatibility
4. Sends screenshots and user instructions to the AI model
5. Receives structured actions such as click, scroll, type, keypress, wait, and drag
6. Rescales model outputs back to real device coordinates
7. Executes the actions on the device or simulator
8. Validates assertions and handles failures
9. Repeats until task completion

---

<h2 id="cli-and-automation">CLI & Automation</h2>

The desktop app is the primary way to use `droid-cua`.

For CI, scripting, or advanced workflows, `droid-cua` also includes a CLI for running saved instructions headlessly.

Desktop projects can also keep run reports in a results folder, including JUnit XML output that the app can read back as project history.

Install:

```sh
npm install -g @loadmill/droid-cua
```

Examples:

```sh
# Interactive CLI
droid-cua

# Headless Android run
droid-cua --avd adb:emulator-5554 --instructions tests/login.dcua

# Headless iOS simulator run
droid-cua --platform ios --avd "iPhone 16" --instructions tests/login.dcua
```

Supported CLI options include:
- `--avd`
- `--platform`
- `--instructions`
- `--record`
- `--debug`

---

<h2 id="release-artifacts">Release Artifacts</h2>

This repository contains public release artifacts for `droid-cua`.

Current public distribution points:
- Desktop app DMG via [GitHub Releases](https://github.com/loadmill/droid-cua-release/releases)
- CLI via [npm](https://www.npmjs.com/package/@loadmill/droid-cua)

Current desktop availability:
- macOS Apple Silicon

---

<h2 id="license">License</h2>

© 2025 Loadmill. All rights reserved.
