--- 来源：https://developer.apple.com/documentation/SwiftUI/AssistiveAccess
抓取时间：2025-12-02T17:43:46Z

---

# AssistiveAccess

**Structure**

一个用于在 iOS 和 iPadOS 上呈现辅助功能界面的场景。在其他平台上，此场景未使用。

## 声明

```swift
struct AssistiveAccess<Content> where Content : View
```

## 初始化器

- **init(content:)**：创建一个辅助功能场景。

## 使用辅助功能

- **accessibilityAssistiveAccessEnabled**：一个布尔值，指示是否正在使用辅助功能。

## 符合以下规范

- Scene


---
source: https://developer.apple.com/documentation/SwiftUI/AssistiveAccess
crawled: 2025-12-02T17:43:46Z
---

# AssistiveAccess

**Structure**

A scene that presents an interface appropriate for Assistive Access on iOS and iPadOS. On other platforms, this scene is unused.

## Declaration

```swift
struct AssistiveAccess<Content> where Content : View
```

## Initializers

- **init(content:)**: Creates an Assistive Access scene.

## Using assistive access

- **accessibilityAssistiveAccessEnabled**: A Boolean value that indicates whether Assistive Access is in use.

## Conforms To

- Scene

