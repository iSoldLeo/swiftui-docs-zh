---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/background(内容：)
抓取时间： 2025-12-01T11:49:36Z
---

# background(content:)

**实例方法**

为托管配置的外层单元格设置背景内容。

## 声明

```swift
func background<B>(@ViewBuilder content: () -> B) -> UIHostingConfiguration<Content, B> where B : View
```

## 讨论

下面的示例将自定义视图设置为单元格的背景：

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.background {
    MyBackgroundView()
}
```

## 设置背景

- **background(_:)**：设置主机配置的外层单元格的背景内容。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/background(content:)
crawled: 2025-12-01T11:49:36Z
---

# background(content:)

**Instance Method**

Sets the background contents for the hosting configuration’s enclosing cell.

## Declaration

```swift
func background<B>(@ViewBuilder content: () -> B) -> UIHostingConfiguration<Content, B> where B : View
```

## Discussion

The following example sets a custom view to the background of the cell:

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.background {
    MyBackgroundView()
}
```

## Setting the background

- **background(_:)**: Sets the background contents for the hosting configuration’s enclosing cell.

