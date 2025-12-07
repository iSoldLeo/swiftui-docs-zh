--- 来源：https://developer.apple.com/documentation/SwiftUI/View/allowsWindowActivationEvents(_:)

抓取时间：2025-12-02T17:41:22Z

---

# allowedWindowActivationEvents(_:)

**实例方法**

配置此视图层级结构中的手势是否可以处理激活包含窗口的事件。

## 声明

```swift
nonisolated func allowsWindowActivationEvents(_ value: Bool?) -> some View

```

## 参数

- **value**：一个布尔值，指示此视图层级结构中的手势是否可以处理激活包含窗口的事件。如果为 `nil`，或者修饰符不存在，则行为将继承自视图的祖先。

## 说明

层级结构中更高级别的视图可以覆盖您在此视图上设置的值。在以下示例中，点击 `Rectangle` 的手势无法处理激活包含窗口的事件，因为外部 `allowsWindowActivationEvents(_:)` 视图修饰符覆盖了内部的：

```swift
HStack {
    Rectangle()
        .onTapGesture { ... }
        .allowsWindowActivationEvents()
}
.allowsWindowActivationEvents(false)
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/allowsWindowActivationEvents(_:)
crawled: 2025-12-02T17:41:22Z
---

# allowsWindowActivationEvents(_:)

**Instance Method**

Configures whether gestures in this view hierarchy can handle events that activate the containing window.

## Declaration

```swift
nonisolated func allowsWindowActivationEvents(_ value: Bool?) -> some View

```

## Parameters

- **value**: A Boolean value that indicates whether gestures in this view hierarchy can handle events that activate the containing window. If `nil`, or if the modifier is not present, the behavior will be inherited from the view’s ancestors.

## Discussion

Views higher in the hierarchy can override the value you set on this view. In the following example, the tap gesture on the `Rectangle` won’t handle events that activate the containing window because the outer `allowsWindowActivationEvents(_:)` view modifier overrides the inner one:

```swift
HStack {
    Rectangle()
        .onTapGesture { ... }
        .allowsWindowActivationEvents()
}
.allowsWindowActivationEvents(false)
```





