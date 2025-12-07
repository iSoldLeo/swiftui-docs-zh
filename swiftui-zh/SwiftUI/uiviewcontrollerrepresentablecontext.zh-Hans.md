---
来源： https://developer.apple.com/documentation/swiftui/uiviewcontrollerrepresentablecontext
抓取时间： 2025-12-04T11:33:40Z
---

# UIViewControllerRepresentableContext

**Structure**

有关系统状态的上下文信息，用于创建和更新 UIKit 视图控制器。

## 声明

```swift
@MainActor @preconcurrency struct UIViewControllerRepresentableContext<Representable> where Representable : UIViewControllerRepresentable
```

## 概览

[UIViewControllerRepresentableContext](UIViewControllerRepresentableContext.zh-Hans.md)结构包含有关系统当前状态的详细信息。在创建和更新视图控制器时，系统会创建这些结构之一，并将其传递给自定义[UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) 实例的相应方法。使用此结构中的信息来配置视图控制器。例如，使用所提供的环境值配置视图控制器和视图的外观。请勿自行创建此结构。

## 协调视图控制器的交互

- **coordinator**：视图的关联协调器。
- **transaction**：当前事务。

## 获取环境数据

- **environment**：描述系统当前状态的环境值。

### 实例方法

- **animate(changes:completion:)**：使用当前事务中的动画演示更改。

## 将 UIKit 视图添加到 SwiftUI 视图层次结构中

- **UIViewRepresentable**：UIKit 视图的封装器，用于将该视图集成到 SwiftUI 视图层次结构中。
- **UIViewRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图。
- **UIViewControllerRepresentable**：表示 UIKit 视图控制器的视图。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/uiviewcontrollerrepresentablecontext
crawled: 2025-12-04T11:33:40Z
---

# UIViewControllerRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update your UIKit view controller.

## Declaration

```swift
@MainActor @preconcurrency struct UIViewControllerRepresentableContext<Representable> where Representable : UIViewControllerRepresentable
```

## Overview

A [UIViewControllerRepresentableContext](UIViewControllerRepresentableContext.zh-Hans.md) structure contains details about the current state of the system. When creating and updating your view controller, the system creates one of these structures and passes it to the appropriate method of your custom [UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) instance. Use the information in this structure to configure your view controller. For example, use the provided environment values to configure the appearance of your view controller and views. Don’t create this structure yourself.

## Coordinating view controller interactions

- **coordinator**: The view’s associated coordinator.
- **transaction**: The current transaction.

## Getting the environment data

- **environment**: Environment values that describe the current state of the system.

## Instance Methods

- **animate(changes:completion:)**: Animates changes using the animation in the current transaction.

## Adding UIKit views to SwiftUI view hierarchies

- **UIViewRepresentable**: A wrapper for a UIKit view that you use to integrate that view into your SwiftUI view hierarchy.
- **UIViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view.
- **UIViewControllerRepresentable**: A view that represents a UIKit view controller.

## Conforms To

- Sendable
- SendableMetatype

