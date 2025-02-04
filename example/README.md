# app_installer_example

Demonstrates how to use the app_installer plugin.

[中文使用文档](https://github.com/yy1300326388/app_installer/tree/master/example/README_CN.md)

## Getting Started

- Open Store

```dart
/// App Info
String androidAppId = 'com.tengyue360.student';
String iOSAppId = '1440249706';

AppInstaller.goStore(androidAppId, iOSAppId);
```

- Open Review

```dart
AppInstaller.goStore(androidAppId, iOSAppId, review: true);
```

- Install Apk

```dart
AppInstaller.installApk('/sdcard/apk/app-debug.apk');
```

> AndroidManifest.xml

```xml
<!-- Provider -->
<provider
    android:name="androidx.core.content.FileProvider"
    android:authorities="${applicationId}.fileProvider"
    android:exported="false"
    android:grantUriPermissions="true">
    <meta-data
        android:name="android.support.FILE_PROVIDER_PATHS"
        android:resource="@xml/file_paths" />
</provider>
```

> android/app/src/main/res/xml/file_paths.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<paths>
    <external-path path="Android/data/packagename/" name="files_root" />
    <external-path path="." name="external_storage_root" />
</paths>

//Replace packagename with your app package name
```
