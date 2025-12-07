---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/horizontalSizeClass
抓取时间： 2025-12-02T17:39:13Z
---

# 水平尺寸类

**实例属性**

该环境的水平尺寸类别。

## 声明

```swift
@backDeployed(before: macOS 14.0, tvOS 17.0, watchOS 10.0)
var horizontalSizeClass: UserInterfaceSizeClass? { get set }
```

## 讨论

读取该环境值时，会收到一个 [UserInterfaceSizeClass](../UserInterfaceSizeClass.zh-Hans.md) 值。该值会告诉你读取该值的视图可用的水平空间大小。通过使用[Environment](../Environment.zh-Hans.md) 属性包装器创建一个属性，您可以像读取其他[EnvironmentValues](../EnvironmentValues.zh-Hans.md) 属性一样读取该 size 类：

```swift
@Environment(\.horizontalSizeClass) private var horizontalSizeClass
```

SwiftUI 基于多个因素设置此大小类，包括

- 当前设备类型。
- 设备的方向。
- iPad 上 "滑过 "和 "分割视图 "的外观。

一些内置视图会根据尺寸类别改变行为。例如，当水平尺寸类别为[NavigationView](../NavigationView.zh-Hans.md)时，[NavigationView](../NavigationView.zh-Hans.md)会显示多栏视图，反之则显示单栏视图。您还可以通过读取尺寸类别和调整视图来调整自定义视图的外观。如果这样做，请准备好在应用程序运行时处理尺寸类的更改，因为设备方向等因素可能会在运行时发生变化。

在 watchOS 中，水平尺寸类始终为 [compact](../UserInterfaceSizeClass/compact.zh-Hans.md)。在 macOS 和 tvOS 中，它始终是 [regular](../UserInterfaceSizeClass/regular.zh-Hans.md)。

在 macOS 14.0、tvOS 17.0 和 watchOS 10.0 之前的环境中，不支持写入水平尺寸类。

## 对界面特征做出反应

- **isLuminanceReduced**：布尔值，表示显示屏或环境当前是否需要降低亮度。
- **displayScale**：该环境的显示比例。
- **pixelLength**：屏幕上像素的大小。
- **verticalSizeClass**：该环境的垂直尺寸类别。
- **UserInterfaceSizeClass**：一组表示视图可用视觉尺寸的值。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/horizontalSizeClass
crawled: 2025-12-02T17:39:13Z
---

# horizontalSizeClass

**Instance Property**

The horizontal size class of this environment.

## Declaration

```swift
@backDeployed(before: macOS 14.0, tvOS 17.0, watchOS 10.0)
var horizontalSizeClass: UserInterfaceSizeClass? { get set }
```

## Discussion

You receive a [UserInterfaceSizeClass](../UserInterfaceSizeClass.zh-Hans.md) value when you read this environment value. The value tells you about the amount of horizontal space available to the view that reads it. You can read this size class like any other of the [EnvironmentValues](../EnvironmentValues.zh-Hans.md), by creating a property with the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
@Environment(\.horizontalSizeClass) private var horizontalSizeClass
```

SwiftUI sets this size class based on several factors, including:

- The current device type.
- The orientation of the device.
- The appearance of Slide Over and Split View on iPad.

Several built-in views change their behavior based on this size class. For example, a [NavigationView](../NavigationView.zh-Hans.md) presents a multicolumn view when the horizontal size class is [regular](../UserInterfaceSizeClass/regular.zh-Hans.md), but a single column otherwise. You can also adjust the appearance of custom views by reading the size class and conditioning your views. If you do, be prepared to handle size class changes while your app runs, because factors like device orientation can change at runtime.

In watchOS, the horizontal size class is always [compact](../UserInterfaceSizeClass/compact.zh-Hans.md). In macOS, and tvOS, it’s always [regular](../UserInterfaceSizeClass/regular.zh-Hans.md).

Writing to the horizontal size class in the environment before macOS 14.0, tvOS 17.0, and watchOS 10.0 is not supported.

## Reacting to interface characteristics

- **isLuminanceReduced**: A Boolean value that indicates whether the display or environment currently requires reduced luminance.
- **displayScale**: The display scale of this environment.
- **pixelLength**: The size of a pixel on the screen.
- **verticalSizeClass**: The vertical size class of this environment.
- **UserInterfaceSizeClass**: A set of values that indicate the visual size available to the view.

