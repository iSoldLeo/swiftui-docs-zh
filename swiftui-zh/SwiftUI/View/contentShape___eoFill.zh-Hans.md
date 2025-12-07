--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contentShape(_:eoFill:)

抓取时间：2025-12-02T17:42:18Z

---

# contentShape(_:eoFill:)

**实例方法**

定义用于命中测试的内容形状。

## 声明

```swift
nonisolated func contentShape<S>(_ shape: S, eoFill: Bool = false) -> some View where S : Shape

```

## 参数

- **shape**：视图的命中测试形状。

- **eoFill**：一个布尔值，指示是否使用奇偶数绕数规则来解释形状。

## 返回值

一个使用给定形状进行命中测试的视图。

## 控制命中测试

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **contentShape(_:_:eoFill:)**：设置此视图的内容形状。

- **ContentShapeKinds**：视图内容形状的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contentShape(_:eoFill:)
crawled: 2025-12-02T17:42:18Z
---

# contentShape(_:eoFill:)

**Instance Method**

Defines the content shape for hit testing.

## Declaration

```swift
nonisolated func contentShape<S>(_ shape: S, eoFill: Bool = false) -> some View where S : Shape

```

## Parameters

- **shape**: The hit testing shape for the view.
- **eoFill**: A Boolean that indicates whether the shape is interpreted with the even-odd winding number rule.

## Return Value

A view that uses the given shape for hit testing.

## Controlling hit testing

- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **contentShape(_:_:eoFill:)**: Sets the content shape for this view.
- **ContentShapeKinds**: A kind for the content shape of a view.

