---
来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:content:)
抓取时间： 2025-12-02T21:48:48Z
---

# init(id:content:)

**Initializer**

创建带有标识符的窗口组。

## 声明

```swift
init(id: String, @ViewBuilder content: () -> Content)
```

## 参数

- **id**：唯一标识窗口组的字符串。在应用程序的窗口组中，标识符必须是唯一的。
- **content**：为组的每个实例创建内容的闭包。

## 讨论

窗口组使用给定视图作为模板来创建组中每个窗口的内容。

## 识别窗口组

- **init(_:id:content:)**：创建带有文本视图标题和标识符的窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:content:)
crawled: 2025-12-02T21:48:48Z
---

# init(id:content:)

**Initializer**

Creates a window group with an identifier.

## Declaration

```swift
init(id: String, @ViewBuilder content: () -> Content)
```

## Parameters

- **id**: A string that uniquely identifies the window group. Identifiers must be unique among the window groups in your app.
- **content**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the given view as a template to form the content of each window in the group.

## Identifying a window group

- **init(_:id:content:)**: Creates a window group with a text view title and an identifier.

