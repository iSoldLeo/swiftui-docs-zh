--- 来源：https://developer.apple.com/documentation/SwiftUI/View/allowsTightening(_:)

抓取时间：2025-12-02T17:35:01Z

---

#allowsTightening(_:)

**实例方法**

设置此视图中的文本是否可以在必要时压缩字符间距以使其适应一行。

## 声明

```swift
nonisolated func allowsTightening(_ flag: Bool) -> some View

```

## 参数

- **flag**：一个布尔值，指示是否在必要时压缩字符间距。

## 返回值

一个可以在必要时压缩字符间距以使其适应一行的视图。

## 说明

使用 `allowsTightening(_:)` 可以启用视图中文本字符间距的压缩，以尝试使文本适应视图的边界。

以下示例展示了两个配置相同的文本视图，它们演示了 `allowsTightening(_:)` 对字符间距压缩的影响：

```swift
VStack {
    Text("This is a wide text element")
        .font(.body)
        .frame(width: 200, height: 50, alignment: .leading)
        .lineLimit(1)
        .allowsTightening(true)

    Text("This is a wide text element")
        .font(.body)
        .frame(width: 200, height: 50, alignment: .leading)
        .lineLimit(1)
        .allowsTightening(false)
}
```

## 控制命中测试

- **contentShape(_:eoFill:)**：定义命中测试的内容形状。

- **contentShape(_:_:eoFill:)**：设置此视图的内容形状。

- **ContentShapeKinds**：视图内容形状的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/allowsTightening(_:)
crawled: 2025-12-02T17:35:01Z
---

# allowsTightening(_:)

**Instance Method**

Sets whether text in this view can compress the space between characters when necessary to fit text in a line.

## Declaration

```swift
nonisolated func allowsTightening(_ flag: Bool) -> some View

```

## Parameters

- **flag**: A Boolean value that indicates whether the space between characters compresses when necessary.

## Return Value

A view that can compress the space between characters when necessary to fit text in a line.

## Discussion

Use `allowsTightening(_:)` to enable the compression of inter-character spacing of text in a view to try to fit the text in the view’s bounds.

In the example below, two identically configured text views show the effects of `allowsTightening(_:)` on the compression of the spacing between characters:

```swift
VStack {
    Text("This is a wide text element")
        .font(.body)
        .frame(width: 200, height: 50, alignment: .leading)
        .lineLimit(1)
        .allowsTightening(true)

    Text("This is a wide text element")
        .font(.body)
        .frame(width: 200, height: 50, alignment: .leading)
        .lineLimit(1)
        .allowsTightening(false)
}
```



## Controlling hit testing

- **contentShape(_:eoFill:)**: Defines the content shape for hit testing.
- **contentShape(_:_:eoFill:)**: Sets the content shape for this view.
- **ContentShapeKinds**: A kind for the content shape of a view.

