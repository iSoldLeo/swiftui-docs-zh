---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/minSize(宽度:高度:)
抓取时间： 2025-12-03T07:00:27Z
---

# minSize(width:height:)

**实例方法**

设置配置的最小尺寸。

## 声明

```swift
func minSize(width: CGFloat? = nil, height: CGFloat? = nil) -> UIHostingConfiguration<Content, Background>
```

## 参数

- **width**：宽度维度使用的值。如果值为 `nil`，则表示应使用系统默认值。
- **height**：高度维度使用的值。如果值为 `nil`，则表示应使用系统默认值。

## 讨论

使用此修改器可将配置的相关单元格大小调整到特定的最小值。下面的示例允许将单元格压缩为零：

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.minSize(width: 0, height: 0)
```

## 设置大小

- **minSize()**：设置配置的最小尺寸。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/minSize(width:height:)
crawled: 2025-12-03T07:00:27Z
---

# minSize(width:height:)

**Instance Method**

Sets the minimum size for the configuration.

## Declaration

```swift
func minSize(width: CGFloat? = nil, height: CGFloat? = nil) -> UIHostingConfiguration<Content, Background>
```

## Parameters

- **width**: The value to use for the width dimension. A value of `nil` indicates that the system default should be used.
- **height**: The value to use for the height dimension. A value of `nil` indicates that the system default should be used.

## Discussion

Use this modifier to indicate that a configuration’s associated cell can be resized to a specific minimum. The following example allows the cell to be compressed to zero size:

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.minSize(width: 0, height: 0)
```

## Setting a size

- **minSize()**: Sets the minimum size for the configuration.

