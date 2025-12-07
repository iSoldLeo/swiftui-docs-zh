---
来源： https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:content:)
抓取时间： 2025-12-02T21:48:48Z
---

# init(_:content:)

**Initializer**

创建带有文本视图标题的窗口组。

## 声明

```swift
init(_ title: Text, @ViewBuilder content: () -> Content)
```

## 参数

- **title**：用于组标题的 [Text](../Text.zh-Hans.md) 视图。
- **content**：为组的每个实例创建内容的闭包。

### 讨论

窗口组使用给定视图作为模板来创建组中每个窗口的内容。系统会在用户界面中使用标题来区分窗口组，例如在与该组相关的命令名称中。



## 创建窗口组

- **init(content:)**：创建窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:content:)
crawled: 2025-12-02T21:48:48Z
---

# init(_:content:)

**Initializer**

Creates a window group with a text view title.

## Declaration

```swift
init(_ title: Text, @ViewBuilder content: () -> Content)
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use for the group’s title.
- **content**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the given view as a template to form the content of each window in the group. The system uses the title to distinguish the window group in the user interface, such as in the name of commands associated with the group.



## Creating a window group

- **init(content:)**: Creates a window group.

