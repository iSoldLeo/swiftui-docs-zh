--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/automatic
抓取时间：2025-12-03T06:45:28Z

---

# automatic

**类型属性**

基于周围上下文的默认悬停效果。

## 声明

```swift
static var automatic: AutomaticHoverEffect { get }
```

## 讨论

自动效果将解析为应用于当前视图层级的任何 [defaultHoverEffect(_:)](../View/defaultHoverEffect.zh-Hans.md)，或者如果没有定义默认效果，则解析为系统定义的效果。

## 获取内置悬停效果

- **empty**：悬停时不进行任何更改的效果。

- **highlight**：使用光源高亮显示视图以指示位置的悬停效果。

- **lift**：一种悬停效果，使指针滑到视图下方，并随着视图放大而消失，同时产生阴影。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/automatic
crawled: 2025-12-03T06:45:28Z
---

# automatic

**Type Property**

The default hover effect based on the surrounding context.

## Declaration

```swift
static var automatic: AutomaticHoverEffect { get }
```

## Discussion

The automatic effect will resolve to any [defaultHoverEffect(_:)](../View/defaultHoverEffect.zh-Hans.md) applied to the current View hierarchy, or a system-defined effect if no default effect has been defined.

## Getting built-in hover effects

- **empty**: An effect that applies no changes when hovered.
- **highlight**: A hover effect that highlights views using a light source to indicate position.
- **lift**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

