---
title: Basic Commands
localeTitle: Основные команды
---
## Основные команды

Здесь вы найдете список основных команд, чтобы начать разработку приложений для iOS и Android с помощью React Native. Если вы еще не установили его, настоятельно рекомендуется следовать [официальному руководству](https://facebook.github.io/react-native/docs/getting-started.html) .

### Запуск нового проекта

Существуют различные способы загрузки исходного приложения. Вы можете использовать приложение **Expo** или `create-react-native-app` (которое, в свою очередь, использует Expo-Cli), чтобы начать новый проект, но с помощью этого метода вы больше контролируете, что происходит в вашем проекте, и можете общаться, настраивать и писать собственные модули с родными библиотеками для iOS и мобильной платформы Android.
```
react-native init [PROJECT-NAME] 
 cd [PROJECT-NAME] 
```

**Запустить приложение в эмуляторе Android**

Эта команда сама запустит эмулятор Android и установит приложение, которое вы только что создали. Вы должны быть в корне проекта для запуска этой команды.

```
react-native run-android 
```

**Запустить приложение в эмуляторе iOS**

Эта команда делает то же самое, что `react-native run-android` но вместо эмулятора Android он открывает симулятор iPhone.
```
react-native run-ios 
```

**Связывание ссылок с собственными проектами**

Некоторые библиотеки имеют зависимости, которые необходимо связать в собственном коде, созданном для React Native. Если что-то не работает после установки новой библиотеки, возможно, это потому, что вы пропустите этот шаг.
```
react-native link [LIBRARY-NAME] 
```

**Очистить связку**

Если что-то не работает должным образом, возможно, вам нужно очистить и создать новый пакет с помощью этой команды.
```
watchman watch-del-all 
```

**Поддержка декораторов**

JSX по умолчанию не поддерживает декораторов, поэтому вам нужно установить плагин **Babel,** чтобы он работал.
```
npm install babel-plugin-transform-decorators-legacy --save 
 npm install babel-plugin-transform-class-properties --save 
```

### Экспорт APK для запуска в устройстве

С помощью следующих команд вы получите неподписанный apk, чтобы вы могли установить и поделиться с коллегами для целей тестирования. Просто помните, что этот апк не готов к загрузке в App Store или в публичный доступ. Вы найдете свой новый apk в _android / app / build / output / apk / app-debug.apk_

**1\. Отладка сборки пакета**
```
react-native bundle --dev false --platform android --entry-file index.android.js --bundle-output ./android/app/build/intermediates/assets/debug/index.android.bundle --assets-dest ./android/app/build/intermediates/res/merged/debug 
```

**2\. Создать сборку отладки**
```
cd android 
 ./gradlew assembleDebug 

```
