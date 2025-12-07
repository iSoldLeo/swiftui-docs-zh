---
来源： https://developer.apple.com/documentation/SwiftUI/DynamicProperty
抓取时间： 2025-12-02T17:32:17Z
---

# 动态属性

**Protocol**

用于更新视图外部属性的存储变量接口。

## 声明

```swift
protocol DynamicProperty
```

## 概览

在重新计算视图的[body-8kl5o](View/body-8kl5o.zh-Hans.md)之前，视图会给这些属性赋值。

## 更新值

- **update()**：更新存储值的基础值。

## 符合类型

- 无障碍焦点状态
- 应用程序存储
- 绑定
- 环境
- 环境对象
- 撷取请求
- 聚焦状态
- 聚焦绑定
- 聚焦对象
- 聚焦值
- 手势状态
- NSA 应用程序代理适配器
- 名称空间
- 观察对象
- 物理量
- 缩放度量
- 场景存储
- 分段撷取请求
- 状态
- 状态对象
- UIA 应用程序代理适配器
- WKA 应用程序代理适配器
- WKE 扩展代理适配器


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicProperty
crawled: 2025-12-02T17:32:17Z
---

# DynamicProperty

**Protocol**

An interface for a stored variable that updates an external property of a view.

## Declaration

```swift
protocol DynamicProperty
```

## Overview

The view gives values to these properties prior to recomputing the view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md).

## Updating the value

- **update()**: Updates the underlying value of the stored value.

## Conforming Types

- AccessibilityFocusState
- AppStorage
- Binding
- Environment
- EnvironmentObject
- FetchRequest
- FocusState
- FocusedBinding
- FocusedObject
- FocusedValue
- GestureState
- NSApplicationDelegateAdaptor
- Namespace
- ObservedObject
- PhysicalMetric
- ScaledMetric
- SceneStorage
- SectionedFetchRequest
- State
- StateObject
- UIApplicationDelegateAdaptor
- WKApplicationDelegateAdaptor
- WKExtensionDelegateAdaptor

