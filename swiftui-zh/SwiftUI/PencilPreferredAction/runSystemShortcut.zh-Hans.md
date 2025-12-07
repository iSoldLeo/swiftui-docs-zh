---
来源： https://developer.apple.com/documentation/SwiftUI/PencilPreferredAction/runSystemShortcut
抓取时间： 2025-12-03T06:43:43Z
---

# 运行系统快捷方式

**类型属性**

运行系统快捷方式的操作。

## 声明

```swift
static let runSystemShortcut: PencilPreferredAction
```

## 讨论

如果用户在双击或挤压 Apple Pencil 后选择此操作作为首选操作，则您的应用程序永远不会收到用户选择此操作的通知。相反，你只能在应用程序的用户界面中使用这些信息来提醒用户他们的偏好。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilPreferredAction/runSystemShortcut
crawled: 2025-12-03T06:43:43Z
---

# runSystemShortcut

**Type Property**

An action that runs a system shortcut.

## Declaration

```swift
static let runSystemShortcut: PencilPreferredAction
```

## Discussion

If the user selects this as their preferred action to perform after double-tapping or squeezing their Apple Pencil, your app will never be notified when they do. Instead, you should only use this information to remind the user about their preference in your app’s UI.

