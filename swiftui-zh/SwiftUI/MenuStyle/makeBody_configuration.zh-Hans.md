---
来源：https://developer.apple.com/documentation/SwiftUI/MenuStyle/makeBody(配置：)
抓取时间： 2025-12-01T10:58:41Z
---

# makeBody(configuration:)

**实例方法**

创建表示菜单主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：菜单的属性。

## 讨论

系统会为视图层次结构中的每个[Menu](../Menu.zh-Hans.md) 实例调用此方法，其中该样式是当前的菜单样式。

## 创建自定义菜单样式

- **MenuStyle.Configuration**：菜单的属性。
- **Body**：表示菜单主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyle/makeBody(configuration:)
crawled: 2025-12-01T10:58:41Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a menu.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the menu.

## Discussion

The system calls this method for each [Menu](../Menu.zh-Hans.md) instance in a view hierarchy where this style is the current menu style.

## Creating custom menu styles

- **MenuStyle.Configuration**: The properties of a menu.
- **Body**: A view that represents the body of a menu.

