---

来源：https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentablecontext
抓取时间：2025-12-04T11:33:29Z

---

# NSViewControllerRepresentableContext

**Structure**

用于创建和更新 AppKit 视图控制器的系统状态上下文信息。

## 声明

```swift
@MainActor @preconcurrency struct NSViewControllerRepresentableContext<ViewController> where ViewController : NSViewControllerRepresentable
```

## 概述

[NSViewControllerRepresentableContext](NSViewControllerRepresentableContext.zh-Hans.md) 结构包含有关系统当前状态的详细信息。创建和更新视图控制器时，系统会创建此类结构之一，并将其传递给自定义 [NSViewControllerRepresentable](NSViewControllerRepresentable.zh-Hans.md) 实例的相应方法。使用此结构中的信息来配置视图控制器。例如，使用提供的环境变量值来配置视图控制器和视图的外观。请勿自行创建此结构。

## 协调视图相关的交互

- **coordinator**：用于将 AppKit 视图控制器的行为和状态传递给 SwiftUI 对象。

- **transaction**：当前事务。

## 获取当前环境数据

- **environment**：描述系统当前状态的环境数据。

## 实例方法

- **animate(changes:completion:)**：使用当前事务中的动画来实现动画效果。

## 将 AppKit 视图添加到 SwiftUI 视图层级结构

- **NSViewRepresentable**：用于将 AppKit 视图集成到 SwiftUI 视图层级结构中的包装器。

- **NSViewRepresentableContext**：用于创建和更新 AppKit 视图的系统状态上下文信息。

- **NSViewControllerRepresentable**：一个用于将 AppKit 视图控制器集成到 SwiftUI 界面中的包装器。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentablecontext
crawled: 2025-12-04T11:33:29Z
---

# NSViewControllerRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update your AppKit view controller.

## Declaration

```swift
@MainActor @preconcurrency struct NSViewControllerRepresentableContext<ViewController> where ViewController : NSViewControllerRepresentable
```

## Overview

An [NSViewControllerRepresentableContext](NSViewControllerRepresentableContext.zh-Hans.md) structure contains details about the current state of the system. When creating and updating your view controller, the system creates one of these structures and passes it to the appropriate method of your custom [NSViewControllerRepresentable](NSViewControllerRepresentable.zh-Hans.md) instance. Use the information in this structure to configure your view controller. For example, use the provided environment values to configure the appearance of your view controller and views. Don’t create this structure yourself.

## Coordinating view-related interactions

- **coordinator**: An object you use to communicate your AppKit view controller’s behavior and state out to SwiftUI objects.
- **transaction**: The current transaction.

## Getting the current environment data

- **environment**: Environment data that describes the current state of the system.

## Instance Methods

- **animate(changes:completion:)**: Animates changes using the animation in the current transaction.

## Adding AppKit views to SwiftUI view hierarchies

- **NSViewRepresentable**: A wrapper that you use to integrate an AppKit view into your SwiftUI view hierarchy.
- **NSViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view.
- **NSViewControllerRepresentable**: A wrapper that you use to integrate an AppKit view controller into your SwiftUI interface.

## Conforms To

- Sendable
- SendableMetatype

