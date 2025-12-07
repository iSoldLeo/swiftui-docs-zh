---
来源： https://developer.apple.com/documentation/SwiftUI/UserInterfaceSizeClass
抓取时间： 2025-12-02T17:39:14Z
---

# UserInterfaceSizeClass

**Enumeration**

一组表示视图可用视觉尺寸的值。

## 声明

```swift
enum UserInterfaceSizeClass
```

## 概览

读取[horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) 或 [verticalSizeClass](EnvironmentValues/verticalSizeClass.zh-Hans.md) 环境值时，您会收到一个尺寸类别值。该值会告诉你视图在给定方向上的可用空间大小。通过使用[Environment](Environment.zh-Hans.md) 属性包装器创建属性，您可以像读取其他[EnvironmentValues](EnvironmentValues.zh-Hans.md) 属性一样读取 size 类：

```swift
@Environment(\.horizontalSizeClass) private var horizontalSizeClass
@Environment(\.verticalSizeClass) private var verticalSizeClass
```

SwiftUI 根据几个因素设置大小类，包括

- 当前设备类型。
- 设备的方向。
- iPad 上 "滑过 "和 "分割视图 "的外观。

一些内置视图会根据尺寸类别改变行为。例如，当水平尺寸类别为[NavigationView](NavigationView.zh-Hans.md)时，[regular](UserInterfaceSizeClass/regular.zh-Hans.md)会显示多栏视图，反之则显示单栏视图。您还可以通过读取尺寸类别和调整视图来调整自定义视图的外观。如果这样做，请准备好在应用程序运行时处理尺寸类的更改，因为设备方向等因素可能会在运行时发生变化。

## 获取大小类

- **UserInterfaceSizeClass.compact**：紧凑尺寸类。
- **UserInterfaceSizeClass.regular**：常规尺寸类。

## 创建一个尺寸类

- **init(_:)**：从指定的 UIKit 大小类创建 SwiftUI 大小类。

## 对界面特征做出反应

- **isLuminanceReduced**：布尔值，表示显示屏或环境当前是否需要降低亮度。
- **displayScale**：该环境的显示比例。
- **pixelLength**：屏幕上像素的大小。
- **horizontalSizeClass**：该环境的水平尺寸级别。
- **verticalSizeClass**：该环境的垂直尺寸级别。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/UserInterfaceSizeClass
crawled: 2025-12-02T17:39:14Z
---

# UserInterfaceSizeClass

**Enumeration**

A set of values that indicate the visual size available to the view.

## Declaration

```swift
enum UserInterfaceSizeClass
```

## Overview

You receive a size class value when you read either the [horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) or [verticalSizeClass](EnvironmentValues/verticalSizeClass.zh-Hans.md) environment value. The value tells you about the amount of space available to your views in a given direction. You can read the size class like any other of the [EnvironmentValues](EnvironmentValues.zh-Hans.md), by creating a property with the [Environment](Environment.zh-Hans.md) property wrapper:

```swift
@Environment(\.horizontalSizeClass) private var horizontalSizeClass
@Environment(\.verticalSizeClass) private var verticalSizeClass
```

SwiftUI sets the size class based on several factors, including:

- The current device type.
- The orientation of the device.
- The appearance of Slide Over and Split View on iPad.

Several built-in views change their behavior based on the size class. For example, a [NavigationView](NavigationView.zh-Hans.md) presents a multicolumn view when the horizontal size class is [regular](UserInterfaceSizeClass/regular.zh-Hans.md), but a single column otherwise. You can also adjust the appearance of custom views by reading the size class and conditioning your views. If you do, be prepared to handle size class changes while your app runs, because factors like device orientation can change at runtime.

## Getting size classes

- **UserInterfaceSizeClass.compact**: The compact size class.
- **UserInterfaceSizeClass.regular**: The regular size class.

## Creating a size class

- **init(_:)**: Creates a SwiftUI size class from the specified UIKit size class.

## Reacting to interface characteristics

- **isLuminanceReduced**: A Boolean value that indicates whether the display or environment currently requires reduced luminance.
- **displayScale**: The display scale of this environment.
- **pixelLength**: The size of a pixel on the screen.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **verticalSizeClass**: The vertical size class of this environment.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

