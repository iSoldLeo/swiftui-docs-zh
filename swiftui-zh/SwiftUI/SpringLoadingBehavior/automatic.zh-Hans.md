--- 来源：https://developer.apple.com/documentation/SwiftUI/SpringLoadingBehavior/automatic
抓取时间：2025-12-03T06:47:44Z
---

# automatic

**类型属性**

自动 Spring 加载行为。

## 声明

```swift
static let automatic: SpringLoadingBehavior
```

## 说明

此属性会将 Spring 加载行为与组件的默认行为进行比较。某些组件（例如 `TabView`）默认启用 Spring 加载；而其他组件则不启用。

## 获取行为

- **enabled**：将为适用的视图启用 Spring 加载交互。

- **disabled**：将为适用的视图禁用 Spring 加载交互。


---
source: https://developer.apple.com/documentation/SwiftUI/SpringLoadingBehavior/automatic
crawled: 2025-12-03T06:47:44Z
---

# automatic

**Type Property**

The automatic spring loading behavior.

## Declaration

```swift
static let automatic: SpringLoadingBehavior
```

## Discussion

This defers to default component behavior for spring loading. Some components, such as `TabView`, will default to allowing spring loading; while others do not.

## Getting the behaviors

- **enabled**: Spring loaded interactions will be enabled for applicable views.
- **disabled**: Spring loaded interactions will be disabled for applicable views.

