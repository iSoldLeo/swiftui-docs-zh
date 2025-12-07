---
来源： https://developer.apple.com/documentation/SwiftUI/SpringLoadingBehavior
抓取时间： 2025-12-02T17:42:57Z
---

# SpringLoadingBehavior

**Structure**

控制视图弹簧加载行为的选项。

## 声明

```swift
struct SpringLoadingBehavior
```

## 概览

使用该类型的值时，应同时使用[springLoadingBehavior(_:)](View/springLoadingBehavior.zh-Hans.md)修饰符。

## 获取行为

- **automatic**：自动弹簧加载行为。
- **enabled**：将为适用的视图启用弹簧加载交互。
- **disabled**：将禁用适用视图中的弹簧加载交互。

## 配置弹簧加载

- **springLoadingBehavior(_:)**：设置此视图的弹簧加载行为。
- **springLoadingBehavior**：与此环境关联的视图的弹簧加载交互行为。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SpringLoadingBehavior
crawled: 2025-12-02T17:42:57Z
---

# SpringLoadingBehavior

**Structure**

The options for controlling the spring loading behavior of views.

## Declaration

```swift
struct SpringLoadingBehavior
```

## Overview

Use values of this type with the [springLoadingBehavior(_:)](View/springLoadingBehavior.zh-Hans.md) modifier.

## Getting the behaviors

- **automatic**: The automatic spring loading behavior.
- **enabled**: Spring loaded interactions will be enabled for applicable views.
- **disabled**: Spring loaded interactions will be disabled for applicable views.

## Configuring spring loading

- **springLoadingBehavior(_:)**: Sets the spring loading behavior this view.
- **springLoadingBehavior**: The behavior of spring loaded interactions for the views associated with this environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

