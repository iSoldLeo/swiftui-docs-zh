--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:image:content:)

抓取时间：2025-12-03T05:31:22Z

---

# init(_:image:content:)

**Initializer**

创建一个菜单栏附加组件，并使用图片作为项目标签。提供的标题将由辅助功能系统使用。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：用于项目辅助功能标签的本地化字符串键。

- **image**：用作标签的图片资源。

- **content**：用户选择项目时显示的 `View`。

## 讨论

此项目定义了 `App` 的主场景。

当用户从系统菜单栏中移除此项目时，应用程序将自动退出。因此，它不应与 `App` 中的其他场景类型一起使用。

## 创建带有图像的菜单栏附加项

- **init(_:image:isInserted:content:)**：创建一个带有图像的菜单栏附加项，该图像将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:content:)**：创建一个带有系统图像的菜单栏附加项，该图像将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:isInserted:content:)**：创建一个带有系统图像的菜单栏附加项，该图像将用作项目标签。提供的标题将由辅助功能系统使用。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:image:content:)
crawled: 2025-12-03T05:31:22Z
---

# init(_:image:content:)

**Initializer**

Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The localized string key to use for the accessibility label of the item.
- **image**: The image resource to use as the label.
- **content**: A `View` to display when the user selects the item.

## Discussion

The item defines the primary scene of an `App`.

When this item is removed from the system menu bar by the user, the application will be automatically quit. As such, it should not be used in conjunction with other scene types in your `App`.

## Creating a menu bar extra with an image

- **init(_:image:isInserted:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:isInserted:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.

