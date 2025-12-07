---
来源： https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(内容：)
抓取时间： 2025-12-02T21:48:47Z
---

# init(content:)

**Initializer**

创建窗口组。

## 声明

```swift
init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：为组的每个实例创建内容的闭包。

## 讨论

窗口组使用给定视图作为模板来创建组中每个窗口的内容。

## 创建窗口组

- **init(_:content:)**：创建带有文本视图标题的窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(content:)
crawled: 2025-12-02T21:48:47Z
---

# init(content:)

**Initializer**

Creates a window group.

## Declaration

```swift
init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the given view as a template to form the content of each window in the group.

## Creating a window group

- **init(_:content:)**: Creates a window group with a text view title.

