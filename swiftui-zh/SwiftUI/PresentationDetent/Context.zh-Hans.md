---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationDetent/Context
抓取时间： 2025-12-03T06:02:30Z
---

# PresentationDetent.Context

**Structure**

用于计算演示高度的信息。

## 声明

```swift
@dynamicMemberLookup struct Context
```

## 获取高度

- **maxDetentValue**：演示文稿显示的高度。

## 支持类型

- **subscript(dynamicMember:)**：从环境中返回 keyPath 指定的值。

## 创建自定义制动器

- **custom(_:)**：计算高度的自定义制动效果。
- **fraction(_:)**：具有指定分数高度的自定义制动钳。
- **height(_:)**：具有指定高度的自定义制动块。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationDetent/Context
crawled: 2025-12-03T06:02:30Z
---

# PresentationDetent.Context

**Structure**

Information that you use to calculate the presentation’s height.

## Declaration

```swift
@dynamicMemberLookup struct Context
```

## Getting the height

- **maxDetentValue**: The height that the presentation appears in.

## Supporting types

- **subscript(dynamicMember:)**: Returns the value specified by the keyPath from the environment.

## Creating custom detents

- **custom(_:)**: A custom detent with a calculated height.
- **fraction(_:)**: A custom detent with the specified fractional height.
- **height(_:)**: A custom detent with the specified height.

