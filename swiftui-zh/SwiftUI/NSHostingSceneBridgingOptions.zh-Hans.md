--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions
抓取时间：2025-12-02T17:44:44Z

---

# NSHostingSceneBridgingOptions

**Structure**

用于设置宿主视图和控制器如何管理关联窗口的选项。

## 声明

```swift
struct NSHostingSceneBridgingOptions
```

## 获取桥接选项

- **all**：宿主视图的关联窗口的标题栏和工具栏将填充来自各自修饰符的值。

- **title**：宿主视图关联的窗口的标题和副标题将分别填充为 `navigationTitle(_:)` 和 `navigationSubtitle(_:)` 修饰符的值。

- **toolbars**：宿主视图关联的窗口的工具栏将填充为 `toolbar(content:)` 修饰符提供的所有项目。

## 创建桥接选项

- **init(rawValue:)**：从原始值创建新集。

- **rawValue**：原始值。

## 在 AppKit 中显示 SwiftUI 视图

- **统一应用动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。

- **NSHostingController**：一个承载 SwiftUI 视图层级的 AppKit 视图控制器。

- **NSHostingView**：一个承载 SwiftUI 视图层级的 AppKit 视图。

- **NSHostingMenu**：一个 AppKit 菜单，其菜单项由 SwiftUI 视图定义。

- **NSHostingSizingOptions**：用于设置承载视图和控制器的内容大小如何反映到自动布局约束中的选项。

- **NSHostingSceneRepresentation**：一个承载并可呈现 SwiftUI 场景的 AppKit 类型。

## 符合以下协议：

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSceneBridgingOptions
crawled: 2025-12-02T17:44:44Z
---

# NSHostingSceneBridgingOptions

**Structure**

Options for how hosting views and controllers manage aspects of the associated window.

## Declaration

```swift
struct NSHostingSceneBridgingOptions
```

## Geting bridging options

- **all**: The hosting view’s associated window will have both its title bars and toolbars populated with values from their respective modifiers.
- **title**: The hosting view’s associated window will have its title and subtitle populated with the values provided to the `navigationTitle(_:)` and `navigationSubtitle(_:)` modifiers, respectively.
- **toolbars**: The hosting view’s associated window will have its toolbar populated with any items provided to the `toolbar(content:)` modifier.

## Creating a bridging options

- **init(rawValue:)**: Creates a new set from a raw value.
- **rawValue**: The raw value.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

