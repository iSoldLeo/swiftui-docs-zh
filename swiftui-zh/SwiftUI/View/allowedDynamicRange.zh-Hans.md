--- 来源：https://developer.apple.com/documentation/SwiftUI/View/allowedDynamicRange(_:)

抓取时间：2025-12-01T10:22:54Z

---

# allowedDynamicRange(_:)

**实例方法**

返回一个配置了指定动态范围的新视图。

## 声明

```swift
nonisolated func allowedDynamicRange(_ range: Image.DynamicRange?) -> some View

```

## 参数

- **range**：请求的动态范围，如果为 nil 则恢复默认的动态范围。

## 返回值

一个新视图。

## 说明

以下示例在视图层级结构中启用 HDR 渲染：

```swift
MyView().allowedDynamicRange(.high)
```

## 颜色和图案

- **backgroundStyle(_:)**：设置指定的样式以渲染视图中的背景。

- **foregroundStyle(_:)**：设置视图的前景色元素使用指定的样式。

- **foregroundStyle(_:_:)**：设置子视图前景色样式的主样式和次样式。

- **foregroundStyle(_:_:_:)**：设置前景色样式的主样式、次样式和三级样式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/allowedDynamicRange(_:)
crawled: 2025-12-01T10:22:54Z
---

# allowedDynamicRange(_:)

**Instance Method**

Returns a new view configured with the specified allowed dynamic range.

## Declaration

```swift
nonisolated func allowedDynamicRange(_ range: Image.DynamicRange?) -> some View

```

## Parameters

- **range**: The requested dynamic range, or nil to restore the default allowed range.

## Return Value

A new view.

## Discussion

The following example enables HDR rendering within a view hierarchy:

```swift
MyView().allowedDynamicRange(.high)
```

## Colors and patterns

- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.

