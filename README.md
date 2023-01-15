# <img src="https://user-images.githubusercontent.com/70295997/212560102-5b3e9147-76e9-41f3-b5c8-54a8b9ce03f1.png" width=40> Testing Mobile Apps on Emulators vs Simulators

Real devices come with a great value and benefits, but also with their own costs. Mobile simulators and emulators can offer valuable benefits for both developers and testers, but it's worth noting that they also have limitations.

## Emulators and Simulators

In mobile testing, an __emulator__ is a software that mimics the functionality of a real Android device and allows you to test your app on it. An emulator mimics the hardware and OS of the device. 
A __simulator__, on the other hand, is a virtual device for testing iOS apps on a Mac host, such as simulating the behavior of an iPhone or iPad.

Emulators provide an operating environment that closely resembles the functionality and capabilities of a mobile device model, like:
- Emulated incoming phone calls and text messages.
- Various network speeds.
- Location services
- Device orientation and rotation.
- Hardware sensors.

Simulators can be useful for early testing of iOS apps by creating a simulated environment that mimics the functionality of a specific mobile device model. However, it's important to note that simulators have limitations and should not be relied upon for testing of hardware components, gestures, or real-world user scenarios. They are best for lightweight functional testing.

__Emulators vs. Simulators__

An emulator is a desktop app that completely virtualizes all aspects of a real device, including both the hardware and OS. Simulators don’t mimic the hardware or OS. They allow the user to validate application flows, but not in a true production environment.

## Real Devices

Using real devices in mobile testing enables you to test your app on actual hardware, providing an accurate representation of how it performs in a customer's hands. This is useful for ensuring the app's functionality and compatibility on various devices.

## Real Devices vs. Emulators vs. Simulators

The discussion surrounding the use of real devices, emulators, and simulators for mobile testing has been a longstanding and contentious topic in the mobile industry.

__Emulators and simulators__ are best for testing in the early stages of development. Emulators are more suitable for testing external behavior, and simulators for internal behavior.

Testing on __real devices__ provides the most reliable results and is ideal for usability and performance testing. It also allows for more realistic testing by applying real-world conditions and user scenarios.

## Emulators and Simulators - Advantages and Use Cases

Simulators and emulators are both __virtual mobile devices__ that offer various benefits for testing apps.

__Advantages:__
- Variety
  - Simulators and emulators can virtualize a wide range of devices and operating system configurations, making it easy to test on multiple platforms, including those that are only supported through virtual devices. This allows for efficient validation and testing on specific device/OS combinations.
- Price
  - Virtual device solutions, whether local or cloud-based, are significantly more cost-effective than using real devices. As development teams need to test early and at a larger scale, the cost of using real devices for every developer's pre-commit validation can become prohibitive. Virtual devices provide a cost-efficient solution for organizations to scale and execute testing at an earlier stage in the process.
- Starting on a Baseline
  - Using virtual devices allows for a consistent starting point for testing, whereas achieving the same on real devices can be time-consuming and require a factory reset. This consistency and predictability of the virtual device state increases the reliability of automated testing, and eliminates the possibility of unexpected issues such as a locked device by another user. This makes the test execution more consistent and reliable as the device is always in the same state as it was designed for the tests.

__Use Cases:__
- Local Development and Validation
  - Developers and testers commonly use simulators and emulators on their local machines for development, debugging, and local testing. The integrated development environments (IDEs) for native mobile applications, such as Xcode and Android Studio, include virtual device tools as part of the standard installation. Both have become stable and feature-rich in recent years, offering a wide range of capabilities for advanced testing.
- Continuous Integration Testing
  - Virtual device labs are mainly used for continuous integration (CI) testing. As DevOps and Agile methodologies become more popular, teams are testing earlier in the development process, known as shift-left testing. New test automation frameworks that are more aligned with developers’ skills and tools, such as Espresso and XCUITest, enable development teams to increase their test automation coverage.
To run these tests, a proper execution environment, such as a test cloud, is required. Automated tests can be run either in the pre-commit phase, providing fast validation before committing or merging code, or triggered through CI several times a day, providing quick feedback to development teams on recent code changes.

## Real Devices - Advantages

- Nothing ompares to the real thing
  - While virtual devices can be useful for basic testing, truly validating an app's performance requires testing on real devices. Virtual devices are helpful for functional testing, but they may also produce false positives, where the tests pass but the app may have issues in real-world scenarios. This is because simulators and emulators primarily test the main flow of the application (happy path), rather than how it handles negative or extreme cases.
- Better User Interface (UI) Validations
  - To ensure the accuracy of the user interface, validation should be performed on real devices. Additionally, usability issues are more readily apparent when testing on real devices, as opposed to virtual devices. This is particularly true when inputting data via the keyboard, as real devices overlay the app while virtual devices present the keyboard alongside the device interface.
- More Accurate Performance Testing
  - Real devices offer more accurate and dependable measurements of transaction times for performance testing. Additionally, the use of specific hardware in real devices can affect performance differently than virtual devices, which may also render the user interface differently.
- Improved Hardware and Sensor-Related Validations
  - Common scenarios that can be virtualized include those that involve interactions with device hardware and sensors, such as the camera, accelerometer, and biometrics. However, it's worth noting that in some cases, the behavior of real and virtual devices may vary.



