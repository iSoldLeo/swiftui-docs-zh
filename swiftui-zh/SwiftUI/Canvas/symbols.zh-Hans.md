---
来源： https://developer.apple.com/documentation/SwiftUI/Canvas/symbols
抓取时间： 2025-12-02T20:58:02Z
---

# 符号

**实例属性**

提供子视图的视图，可在绘图回调中使用。

## 声明

```swift
var symbols: Symbols
```

## 讨论

使用 `View/tag(_:)` 修饰符对每个子视图进行唯一标记，这样就可以在渲染器中使用 [resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) 方法找到它们。


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas/symbols
crawled: 2025-12-02T20:58:02Z
---

# symbols

**Instance Property**

A view that provides child views that you can use in the drawing callback.

## Declaration

```swift
var symbols: Symbols
```

## Discussion

Uniquely tag each child view using the `View/tag(_:)` modifier, so that you can find them from within your renderer using the [resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) method.

