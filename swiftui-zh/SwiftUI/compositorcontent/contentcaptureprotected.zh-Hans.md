--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/contentcaptureprotected(_:)

抓取时间：2025-12-01T11:21:39Z

---

# contentCaptureProtected(_:)

**实例方法**

将视图标记为在场景捕获事件（例如屏幕截图、屏幕录制、屏幕共享等）期间启用内容保护的视图。

## 声明

```swift
nonisolated func contentCaptureProtected(_ isActive: Bool = true) -> some CompositorContent

```

## 参数

- **isActive**：一个布尔值，用于指定此视图在场景捕获期间出现在屏幕上时是否受到保护。

## 说明

在 visionOS 上，当屏幕上存在带有此修饰符的视图、场景捕获处于活动状态且应用拥有“App Protected Content”（应用受保护内容）权限（可通过 Apple Developer Enterprise Program 获取）时，系统会将整个屏幕内容隐藏。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/contentcaptureprotected(_:)
crawled: 2025-12-01T11:21:39Z
---

# contentCaptureProtected(_:)

**Instance Method**

Marks the view as a view that activates content protection during scene capture events, such as screenshots, screen recordings, screensharing, etc.

## Declaration

```swift
nonisolated func contentCaptureProtected(_ isActive: Bool = true) -> some CompositorContent

```

## Parameters

- **isActive**: A Boolean value that specifies whether this view is protected when present on screen during scene capture.

## Discussion

On visionOS, the system redacts the entire screen when a view marked with this modifier is present on screen, scene capture is active, and the app has the App Protected Content entitlement, available through the Apple Developer Enterprise Program.

