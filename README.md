# Articles App

[Clean Architecture in Flutter](https://medium.com/@yamen.abd98/clean-architecture-in-flutter-mvvm-bloc-dio-79b1615530e1)

[Unit Testing with Clean Architecture in Flutter | Mockito](https://medium.com/@yamen.abd98/unit-testing-in-flutter-with-clean-architecture-49d403645b4d)

[articles-flutter-app source code - GitHub](https://github.com/YAMMEN98/articles-flutter-app/tree/main)

A new Flutter project with Clean Architecture to fetch thw New Work Time
Articles, display article details, and see more about details from url.

## Getting Started

```bash
# 一次性生成 models (*.g.dart)
dart run build_runner build --delete-conflicting-outputs

# 持续生成 models (*.g.dart)
dart run build_runner watch --delete-conflicting-outputs
```

## Prerequisites

- Flutter SDK (Flutter 3.7.2, Dart 2.19.2) current Flutter 3.13.9, Dart 3.1.5
- Android Studio or VS Code
- Dart plugin for your IDE

## Installing

- Clone the repository `git clone https://github.com/YAMMEN98/ny-times-flutter-app.git`
- Open the project in Android Studio or VS Code.
- Run the app on an emulator or physical device.

## Feature

- Get all ny times articles.
- Search articles.
- Filter article by `period`
- Display article details.
- Apply Dark/Light theme.
- Apply localization en/ar languages.
- View Image And Zoom It.
- Create a lane to generate apk automatically when upload code to the main branch.

![Text Coverage](https://github.com/YAMMEN98/ny-times-flutter-app/blob/main/actions.png)

- Apply Unit Testing .

## Folder Structure

### core

`core` 位于 `lib/src/core`, 用于存放配置文件:

- 样式 `styles`
- 国际化 `translations` 或 `locales`
- 路由 `router`
- 工具函数 `utils`
- 网络请求配置 `network`, 配置 `Dio`
- 辅助 `helper`

### shared

`shared` 位于 `lib/src/shared`, 用于存放通用页面、共用组件 (`shared/presentation`)

## Built With

- [Flutter](https://github.com/vedranMv/dataDashboard/releases) - The framework used).
- [The New Work a Times API](https://developer.nytimes.com/) - API used for weather data.

## Unit Test

To run test you should follow the steps:

- run command `flutter test`
- If you want to get coverage file from Unit Test run this.command `flutter test --coverage`

There is many tools to generate text coverage,
we will use [test_cov_console](https://pub.dev/packages/test_cov_console) to generate coverage
report, follow these steps to run it:

- Run the following command to make sure all flutter library is up-to-date `flutter pub get`,

  - Run the following command to generate lcov.info on coverage
    directory `flutter test --coverage`,
  - Run the tool to generate report from lcov.info to the
    console `flutter pub run test_cov_console`,
  - You can follow and see more of parameters
    in [test_cov_console](https://pub.dev/packages/test_cov_console).
  - You Can Output report to CSV file (-c, --csv, -o, --output)
    by `flutter pub run test_cov_console -c --output=coverage/test_coverage.csv`
  - Open CSV file by excel and you will see like this result:

    ![Text Coverage](https://github.com/YAMMEN98/ny-times-flutter-app/blob/main/test_coverage.png)

## TODO

### CI/CD

- 测试
- 代码质量检查 sonarqube
- 打包 `apk`、`aab`, 区分未签名和已签名, 并发布到 Google Play
- 打包 `ips`, 可集成 `codemagic`
