---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/background(_:)
抓取时间： 2025-12-03T07:00:25Z
---

# background(_:)

**实例方法**

设置托管配置的外层单元格的背景内容。

## 声明

```swift
func background<S>(_ style: S) -> UIHostingConfiguration<Content, _UIHostingConfigurationBackgroundView<S>> where S : ShapeStyle
```

## 参数

- **style**：用作单元格背景的形状样式。

## 讨论

下面的示例将自定义视图设置为单元格的背景：

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.background(Color.blue)
```

## 设置背景

- **background(content:)**：设置主机配置的外层单元格的背景内容。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/background(_:)
crawled: 2025-12-03T07:00:25Z
---

# background(_:)

**Instance Method**

Sets the background contents for the hosting configuration’s enclosing cell.

## Declaration

```swift
func background<S>(_ style: S) -> UIHostingConfiguration<Content, _UIHostingConfigurationBackgroundView<S>> where S : ShapeStyle
```

## Parameters

- **style**: The shape style to be used as the background of the cell.

## Discussion

The following example sets a custom view to the background of the cell:

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.background(Color.blue)
```

## Setting the background

- **background(content:)**: Sets the background contents for the hosting configuration’s enclosing cell.

