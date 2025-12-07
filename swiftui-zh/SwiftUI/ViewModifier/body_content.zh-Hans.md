---
来源： https://developer.apple.com/documentation/SwiftUI/ViewModifier/body(内容：)
抓取时间： 2025-11-30T21:31:13Z
---

# body(content:)

**实例方法**

获取调用者的当前正文。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func body(content: Self.Content) -> Self.Body
```

## 讨论

`content`是视图的代理，该视图将应用`Self`所代表的修饰符。

## 创建视图修改器

- **Body**：代表主体的视图类型。
- **ViewModifier.Content**：传递给 `body()` 的内容视图类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewModifier/body(content:)
crawled: 2025-11-30T21:31:13Z
---

# body(content:)

**Instance Method**

Gets the current body of the caller.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func body(content: Self.Content) -> Self.Body
```

## Discussion

`content` is a proxy for the view that will have the modifier represented by `Self` applied to it.

## Creating a view modifier

- **Body**: The type of view representing the body.
- **ViewModifier.Content**: The content view type passed to `body()`.

