---
来源： https://developer.apple.com/documentation/swiftui/nsviewrepresentablecontext
抓取时间： 2025-12-04T11:33:34Z
---

# NSViewRepresentableContext

**Structure**

有关系统状态的上下文信息，用于创建和更新 AppKit 视图。

## 声明

```swift
@MainActor @preconcurrency struct NSViewRepresentableContext<View> where View : NSViewRepresentable
```

## 概览

[NSViewRepresentableContext](NSViewRepresentableContext.zh-Hans.md)结构包含有关系统当前状态的详细信息。在创建和更新视图时，系统会创建这些结构之一，并将其传递给自定义[NSViewRepresentable](NSViewRepresentable.zh-Hans.md) 实例的相应方法。使用此结构中的信息配置视图。例如，使用所提供的环境值配置视图的外观。请勿自行创建此结构。

## 协调与视图相关的交互

- **coordinator**：用于将 AppKit 视图的行为和状态传达给 SwiftUI 对象的实例。
- **transaction**：当前事务。

## 获取当前环境数据

- **environment**：描述系统当前状态的环境数据。

### 实例方法

- **animate(changes:completion:)**：使用当前事务中的动画演示更改。

## 将 AppKit 视图添加到 SwiftUI 视图层次结构中

- **NSViewRepresentable**：封装器，用于将 AppKit 视图集成到 SwiftUI 视图层次结构中。
- **NSViewControllerRepresentable**：封装器，用于将 AppKit 视图控制器集成到 SwiftUI 界面中。
- **NSViewControllerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 AppKit 视图控制器。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/nsviewrepresentablecontext
crawled: 2025-12-04T11:33:34Z
---

# NSViewRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update your AppKit view.

## Declaration

```swift
@MainActor @preconcurrency struct NSViewRepresentableContext<View> where View : NSViewRepresentable
```

## Overview

An [NSViewRepresentableContext](NSViewRepresentableContext.zh-Hans.md) structure contains details about the current state of the system. When creating and updating your view, the system creates one of these structures and passes it to the appropriate method of your custom [NSViewRepresentable](NSViewRepresentable.zh-Hans.md) instance. Use the information in this structure to configure your view. For example, use the provided environment values to configure the appearance of your view. Don’t create this structure yourself.

## Coordinating view-related interactions

- **coordinator**: An instance you use to communicate your AppKit view’s behavior and state out to SwiftUI objects.
- **transaction**: The current transaction.

## Getting the current environment data

- **environment**: Environment data that describes the current state of the system.

## Instance Methods

- **animate(changes:completion:)**: Animates changes using the animation in the current transaction.

## Adding AppKit views to SwiftUI view hierarchies

- **NSViewRepresentable**: A wrapper that you use to integrate an AppKit view into your SwiftUI view hierarchy.
- **NSViewControllerRepresentable**: A wrapper that you use to integrate an AppKit view controller into your SwiftUI interface.
- **NSViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view controller.

## Conforms To

- Sendable
- SendableMetatype

