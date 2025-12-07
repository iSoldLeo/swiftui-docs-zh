---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingControllerSizingOptions
抓取时间： 2025-12-02T17:44:52Z
---

# UIHostingControllerSizingOptions

**Structure**

托管控制器跟踪其内容大小的选项。

## 声明

```swift
struct UIHostingControllerSizingOptions
```

## 获取尺寸选项

- **intrinsicContentSize**：托管控制器的视图在其理想尺寸发生变化时，其内在内容尺寸会自动失效。
- **preferredContentSize**：托管控制器在首选内容大小中跟踪其内容的理想大小。

## 创建大小选项

- **init(rawValue:)**：从原始值创建新的选项集。
- **rawValue**：原始值。

## 在 UIKit 中显示 SwiftUI 视图

- 在 UIKit 中使用 SwiftUI**：了解如何将 SwiftUI 视图纳入 UIKit 应用程序。
- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **UIHostingController**：管理 SwiftUI 视图层次结构的 UIKit 视图控制器。
- **UIHostingConfiguration**：适合托管 SwiftUI 视图层次结构的内容配置。
- **UIHostingSceneDelegate**：扩展了 `UIKit/UISceneDelegate` 以桥接 SwiftUI 场景。

## 符合

- 等价
- 可表达数组字素
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingControllerSizingOptions
crawled: 2025-12-02T17:44:52Z
---

# UIHostingControllerSizingOptions

**Structure**

Options for how a hosting controller tracks its content’s size.

## Declaration

```swift
struct UIHostingControllerSizingOptions
```

## Getting sizing options

- **intrinsicContentSize**: The hosting controller’s view automatically invalidate its intrinsic content size when its ideal size changes.
- **preferredContentSize**: The hosting controller tracks its content’s ideal size in its preferred content size.

## Creating a sizing option

- **init(rawValue:)**: Creates a new option set from a raw value.
- **rawValue**: The raw value.

## Displaying SwiftUI views in UIKit

- **Using SwiftUI with UIKit**: Learn how to incorporate SwiftUI views into a UIKit app.
- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **UIHostingController**: A UIKit view controller that manages a SwiftUI view hierarchy.
- **UIHostingConfiguration**: A content configuration suitable for hosting a hierarchy of SwiftUI views.
- **UIHostingSceneDelegate**: Extends `UIKit/UISceneDelegate` to bridge SwiftUI scenes.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

