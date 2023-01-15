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

- Nothing Compares to the Real Thing
  - While virtual devices can be useful for basic testing, truly validating an app's performance requires testing on real devices. Virtual devices are helpful for functional testing, but they may also produce false positives, where the tests pass but the app may have issues in real-world scenarios. This is because simulators and emulators primarily test the main flow of the application (happy path), rather than how it handles negative or extreme cases.
- Better User Interface (UI) Validations
  - To ensure the accuracy of the user interface, validation should be performed on real devices. Additionally, usability issues are more readily apparent when testing on real devices, as opposed to virtual devices. This is particularly true when inputting data via the keyboard, as real devices overlay the app while virtual devices present the keyboard alongside the device interface.
- More Accurate Performance Testing
  - Real devices offer more accurate and dependable measurements of transaction times for performance testing. Additionally, the use of specific hardware in real devices can affect performance differently than virtual devices, which may also render the user interface differently.
- Improved Hardware and Sensor-Related Validations
  - Common scenarios that can be virtualized include those that involve interactions with device hardware and sensors, such as the camera, accelerometer, and biometrics. However, it's worth noting that in some cases, the behavior of real and virtual devices may vary.

## Balance Virtual and Real Devices

As testing occurs throughout the entire development process, from early stages to deployment and monitoring, it is necessary to utilize both real and virtual devices. A balanced approach that includes both types of platforms is essential for each phase in the application lifecycle.

A proposed approach would be to use a combination of virtual devices for early testing and real devices for later stages, such as usability and performance testing, and for validating the application in real-world scenarios. This will allow teams to take advantage of the benefits of each type of platform and ensure the best possible results.

Phases/Stages:
- Code
  - Local Validation
    - During the development phase, developers should validate their code using either a local device or a virtual device, which is often integrated into the developer's IDE. For UI validation, it's recommended to use real devices rather than virtual ones to ensure that the outcome appears as expected.
  - Pre-Commit Validation
    - Unit and UI unit tests should typically be run on virtual devices (90% of the time). However, there may be instances where developers make changes to components that they anticipate will behave differently on real devices. In such cases, it is recommended to provide developers with on-demand tools that allow them to choose which tests to run and on which platform (virtual or real) to run them. This will enable developers to verify the behavior of their changes on both virtual and real devices and make more informed decisions.
- Build
  - Commit Job
    - This process should run every time a developer makes a commit, performing a basic check to ensure that the change doesn't break the build or cause significant regression. Because of the need to run this job at scale with each commit, these tests should be run on virtual devices to ensure efficient execution.
  - Multi-Merge Validation
    - These jobs validate the last X commits and check if one of them broke the build or caused a regression. This type of job usually runs every few hours or after a certain number of code commits. It runs more tests to provide broader coverage. In this stage, more real devices are introduced into the CI process, typically a mix of 70% virtual devices and 30% real devices should be used. This will provide a balance of efficient execution and realistic testing on real devices.
  - Night Job
    - This job runs regression tests and expands coverage. In this stage, tests are run on real devices to ensure the application's performance in real-world scenarios.

      - _The frequency of the CI process will vary depending on the team's maturity level, it can run one or more times a day. The aim is to create a balance that enables scalability while still providing comprehensive test coverage and insights into the end-user experience. To achieve scalability and enable parallel validation for multiple developers and teams, a typical CI mix might consist of a combination of virtual devices for functional testing and real devices for usability and performance testing. This will allow for efficient execution and provide valuable feedback on the application's overall performance._

- Test
  - Additional testing activities that take place outside the CI process will be run on real devices. The objective of these tests is to validate the overall end-user experience, functional flow coverage, UI validation, and performance testing. All tests (100%) should be run on real devices to ensure the best possible results.
- Monitor
  - While some organizations use Real User Monitoring (RUM) solutions that run on real devices, synthetic monitoring, which involves executing single-use automated tests to measure app performance every 10-15 minutes, also has value. For the most accurate results, it is recommended to use real devices for synthetic monitoring. This will provide the most accurate representation of the end-user experience and performance of the app.


