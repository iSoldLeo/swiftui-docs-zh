---
来源： https://developer.apple.com/documentation/SwiftUI/ControlSize
抓取时间： 2025-12-02T17:36:13Z
---

# 控制尺寸

**Enumeration**

可应用于视图中控件的尺寸类别，如常规或小尺寸。

## 声明

```swift
enum ControlSize
```

## 获取控制尺寸

- **ControlSize.mini**：最小大小的控制版本。
- **ControlSize.small**：对于空间受限的视图，按比例缩小的控制版本。
- **ControlSize.regular**：默认大小的控制版本。
- **ControlSize.large**：显著大小的控制版本。
- **ControlSize.extraLarge**：尺寸很大的控制版本。最大的控制版本。在 visionOS 以外的平台上，解析为 [large](ControlSize/large.zh-Hans.md)。

## 初始化器

- **init(_:)**：从等价的 NSControl.ControlSize 创建控制尺寸。

## 确定控件大小

- **controlSize(_:)**：设置该视图中控件的大小。
- **controlSize**：应用于视图中控件的大小。

## 符合

- CaseIterable
- 可比较
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ControlSize
crawled: 2025-12-02T17:36:13Z
---

# ControlSize

**Enumeration**

The size classes, like regular or small, that you can apply to controls within a view.

## Declaration

```swift
enum ControlSize
```

## Getting control sizes

- **ControlSize.mini**: A control version that is minimally sized.
- **ControlSize.small**: A control version that is proportionally smaller size for space-constrained views.
- **ControlSize.regular**: A control version that is the default size.
- **ControlSize.large**: A control version that is prominently sized.
- **ControlSize.extraLarge**: A control version that is substantially sized. The largest control size. Resolves to [large](ControlSize/large.zh-Hans.md) on platforms other than visionOS.

## Initializers

- **init(_:)**: Creates a control size from its NSControl.ControlSize equivalent.

## Sizing controls

- **controlSize(_:)**: Sets the size for controls within this view.
- **controlSize**: The size to apply to controls within a view.

## Conforms To

- CaseIterable
- Comparable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

