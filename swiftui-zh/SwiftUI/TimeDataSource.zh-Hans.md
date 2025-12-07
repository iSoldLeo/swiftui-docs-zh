--- 来源：https://developer.apple.com/documentation/SwiftUI/TimeDataSource
抓取时间：2025-12-02T17:35:14Z

---

# TimeDataSource

**Structure**

时间相关数据源。

## 声明

```swift
struct TimeDataSource<Value>
```

## 概述

此类型的实例为小组件、动态活动、watchOS 复杂功能以及常规应用提供实时且自动更新的值。[Text](Text.zh-Hans.md)

## 类型属性

- **currentDate**：生成 `Date.now` 的时间数据源。

## 类型方法

- **dateRange(endingAt:)**：生成 `min(date, Date.now)..<date` 的时间数据源。

- **dateRange(startingAt:)**：一个时间数据源，生成 `date..<max(date, Date.now)`。

- **durationOffset(to:)**：一个时间数据源，生成 `Date.now` 与给定 `date` 之间的偏移量，并将其作为 `Duration`。

## 格式化日期和时间

- **SystemFormatStyle**：一个用于实现 Apple 各平台通用设计的格式样式命名空间。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TimeDataSource
crawled: 2025-12-02T17:35:14Z
---

# TimeDataSource

**Structure**

A source of time related data.

## Declaration

```swift
struct TimeDataSource<Value>
```

## Overview

Instances of this type provide [Text](Text.zh-Hans.md) with live and automatically updating values in Widgets, Live Activities, watchOS Complications, and of course regular apps.

## Type Properties

- **currentDate**: A time data source that produces `Date.now`.

## Type Methods

- **dateRange(endingAt:)**: A time data source that produces `min(date, Date.now)..<date`.
- **dateRange(startingAt:)**: A time data source that produces `date..<max(date, Date.now)`.
- **durationOffset(to:)**: A time data source that produces the offset between `Date.now` and the given `date` as a `Duration`.

## Formatting date and time

- **SystemFormatStyle**: A namespace for format styles that implement designs used across Apple’s platformes.

## Conforms To

- Sendable
- SendableMetatype

