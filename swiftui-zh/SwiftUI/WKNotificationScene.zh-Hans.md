---
来源： https://developer.apple.com/documentation/SwiftUI/WKNotificationScene
抓取时间： 2025-12-02T17:20:57Z
---

# WKNotificationScene

**Structure**

收到指定类别的远程或本地通知时出现的场景。

## 声明

```swift
struct WKNotificationScene<Content, Controller> where Content : View, Controller : WKUserNotificationHostingController<Content>
```

## 创建通知场景

- **init(controller:category:)**：创建一个场景，在收到特定类别的远程或本地通知时出现。

## 符合

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/WKNotificationScene
crawled: 2025-12-02T17:20:57Z
---

# WKNotificationScene

**Structure**

A scene which appears in response to receiving the specified category of remote or local notifications.

## Declaration

```swift
struct WKNotificationScene<Content, Controller> where Content : View, Controller : WKUserNotificationHostingController<Content>
```

## Creating a notification scene

- **init(controller:category:)**: Creates a scene that appears in response to receiving a specific category of remote or local notifications.

## Conforms To

- Scene

