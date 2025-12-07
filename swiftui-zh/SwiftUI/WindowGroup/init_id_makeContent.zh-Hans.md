---
来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:makeContent:)
抓取时间： 2025-12-02T21:48:57Z
---

# init(id:makeContent:)

**Initializer**

创建带有标识符的窗口组。

## 声明

```swift
nonisolated init(id: String, @ViewBuilder makeContent: @escaping () -> Content)
```

## 参数

- **id**：唯一标识窗口组的字符串。在应用程序的窗口组中，标识符必须是唯一的。
- **makeContent**：为组的每个实例创建内容的闭包。

## 讨论

窗口组使用给定视图作为模板来创建组中每个窗口的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:makeContent:)
crawled: 2025-12-02T21:48:57Z
---

# init(id:makeContent:)

**Initializer**

Creates a window group with an identifier.

## Declaration

```swift
nonisolated init(id: String, @ViewBuilder makeContent: @escaping () -> Content)
```

## Parameters

- **id**: A string that uniquely identifies the window group. Identifiers must be unique among the window groups in your app.
- **makeContent**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the given view as a template to form the content of each window in the group.

