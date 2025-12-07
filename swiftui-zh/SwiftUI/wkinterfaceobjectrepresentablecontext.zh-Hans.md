--- 来源：https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentablecontext
抓取时间：2025-12-04T11:33:46Z

---

# WKInterfaceObjectRepresentableContext

**Structure**

用于创建和更新 WatchKit 界面对象的系统状态上下文信息。

## 声明

```swift
@MainActor @preconcurrency struct WKInterfaceObjectRepresentableContext<Representable> where Representable : WKInterfaceObjectRepresentable
```

## 概述

[WKInterfaceObjectRepresentableContext](WKInterfaceObjectRepresentableContext.zh-Hans.md) 结构包含有关系统当前状态的详细信息。创建和更新界面对象时，系统会创建此类结构之一，并将其传递给自定义 [WKInterfaceObjectRepresentable](WKInterfaceObjectRepresentable.zh-Hans.md) 实例的相应方法。使用此结构中的信息来配置对象。请勿自行创建此结构。

## 协调交互

- **coordinator**：视图关联的协调器。

- **transaction**：当前事务。

## 获取当前环境数据

- **environment**：当前环境。

## 将 WatchKit 视图添加到 SwiftUI 视图层级结构

- **WKInterfaceObjectRepresentable**：表示 WatchKit 接口对象的视图。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentablecontext
crawled: 2025-12-04T11:33:46Z
---

# WKInterfaceObjectRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update your WatchKit interface object.

## Declaration

```swift
@MainActor @preconcurrency struct WKInterfaceObjectRepresentableContext<Representable> where Representable : WKInterfaceObjectRepresentable
```

## Overview

A [WKInterfaceObjectRepresentableContext](WKInterfaceObjectRepresentableContext.zh-Hans.md) structure contains details about the current state of the system. When creating and updating your interface objects, the system creates one of these structures and passes it to the appropriate method of your custom [WKInterfaceObjectRepresentable](WKInterfaceObjectRepresentable.zh-Hans.md) instance. Use the information in this structure to configure your object. Don’t create this structure yourself.

## Coordinating interactions

- **coordinator**: The view’s associated coordinator.
- **transaction**: The current transaction.

## Getting the current environment data

- **environment**: The current environment.

## Adding WatchKit views to SwiftUI view hierarchies

- **WKInterfaceObjectRepresentable**: A view that represents a WatchKit interface object.

## Conforms To

- Sendable
- SendableMetatype

