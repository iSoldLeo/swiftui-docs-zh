--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions

抓取时间：2025-12-02T17:44:43Z

---

# NSHostingSizingOptions

**Structure**

用于设置宿主视图和控制器如何将其内容的大小反映到自动布局约束中的选项。

## 声明

```swift
struct NSHostingSizingOptions
```

## 获取尺寸选项

- **intrinsicContentSize**：宿主视图创建并更新表示其内容理想尺寸的约束。这些约束反过来会影响宿主视图的 `intrinsicContentSize`。

- **maxSize**：宿主视图创建并更新表示其内容最大尺寸的约束。

- **minSize**：宿主视图创建并更新表示其内容最小尺寸的约束。

- **preferredContentSize**：宿主控制器创建并更新表示其内容理想尺寸的约束。这些约束反过来会影响宿主控制器的 `preferredContentSize`。

- **standardBounds**：宿主视图为其最小、理想和最大尺寸创建约束。

## 创建尺寸选项

- **init(rawValue:)**：根据原始值创建新选项。

- **rawValue**：原始值。

## 在 AppKit 中显示 SwiftUI 视图

- **统一应用动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。

- **NSHostingController**：一个承载 SwiftUI 视图层级的 AppKit 视图控制器。

- **NSHostingView**：一个承载 SwiftUI 视图层级的 AppKit 视图。

- **NSHostingMenu**：一个 AppKit 菜单，其菜单项由 SwiftUI 视图定义。

- **NSHostingSceneRepresentation**：一个 AppKit 类型，可以承载并呈现 SwiftUI 场景。

- **NSHostingSceneBridgingOptions**：用于控制承载视图和控制器如何管理关联窗口的选项。

## 符合以下协议：

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions
crawled: 2025-12-02T17:44:43Z
---

# NSHostingSizingOptions

**Structure**

Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.

## Declaration

```swift
struct NSHostingSizingOptions
```

## Geting sizing options

- **intrinsicContentSize**: The hosting view creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting view’s `intrinsicContentSize`.
- **maxSize**: The hosting view creates and updates constraints that represent its content’s maximum size.
- **minSize**: The hosting view creates and updates constraints that represent its content’s minimum size.
- **preferredContentSize**: The hosting controller creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting controller’s `preferredContentSize`.
- **standardBounds**: The hosting view creates constraints for its minimum, ideal, and maximum sizes.

## Creating a sizing option

- **init(rawValue:)**: Creates a new options from a raw value.
- **rawValue**: The raw value.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

