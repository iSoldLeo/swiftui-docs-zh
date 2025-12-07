--- 来源：https://developer.apple.com/documentation/SwiftUI/AutomaticNavigationTransition
抓取时间：2025-12-03T06:17:13Z

---

# AutomaticNavigationTransition

**Structure**

一种样式，可根据当前上下文自动选择合适的显示过渡效果。

## 声明

```swift
struct AutomaticNavigationTransition
```

## 支持类型

- **ZoomNavigationTransition**：一种导航过渡效果，可将当前视图缩放至给定源视图。使用 `View/matchedTransitionSource(id:namespace:)` 修饰符指定源视图。

## 符合以下规范

- NavigationTransition


---
source: https://developer.apple.com/documentation/SwiftUI/AutomaticNavigationTransition
crawled: 2025-12-03T06:17:13Z
---

# AutomaticNavigationTransition

**Structure**

A style that automatically chooses the appropriate presentation transition for the current context.

## Declaration

```swift
struct AutomaticNavigationTransition
```

## Supporting Types

- **ZoomNavigationTransition**: A navigation transition that zooms the appearing view from a given source view. Indicate the source view using the `View/matchedTransitionSource(id:namespace:)` modifier.

## Conforms To

- NavigationTransition

