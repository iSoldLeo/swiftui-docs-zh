--- 来源：https://developer.apple.com/documentation/SwiftUI/Environment-values
抓取时间：2025-12-02T17:32:18Z

---

# 环境值

**API 集合**

使用环境值在视图层级结构中共享数据。

## 概述

SwiftUI 中的视图可以使用 [Environment](Environment.zh-Hans.md) 属性包装器来响应从环境中读取的配置信息。

视图从其容器视图继承环境值，但会受到 [environment(_:_:)](View/environment.zh-Hans.md) 视图修饰符的显式更改，或受到众多作用于环境值的修饰符的隐式更改。因此，您可以通过修改组容器的环境值来配置整个视图层级结构。

您可以在 [EnvironmentValues](EnvironmentValues.zh-Hans.md) 结构中找到许多内置的环境值。您还可以通过在环境值结构的扩展中定义新属性，并将宏 [Entry()](Entry.zh-Hans.md) 应用于变量声明，来创建自定义属性 [EnvironmentValues](EnvironmentValues.zh-Hans.md)。

## 访问环境值

- **Environment**：一个属性包装器，用于从视图的环境中读取值。

- **EnvironmentValues**：通过视图层次结构传播的环境值集合。

## 创建自定义环境值

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **EnvironmentKey**：用于访问环境中的值的键。

## 修改视图的环境

- **environment(_:)**：将可观察对象放置在视图的环境中。

- **environment(_:_:)**：将指定键路径的环境值设置为给定值。

- **transformEnvironment(_:transform:)**：使用给定函数转换指定键路径的环境值。

## 修改场景环境

- **environment(_:)**：将可观察对象放置在场景环境中。

- **environment(_:_:)**：将指定键路径的环境值设置为给定值。

- **transformEnvironment(_:transform:)**：使用给定函数转换指定键路径的环境值。

## 数据和存储

- **模型数据**：管理应用程序用于驱动其界面的数据。

- **Preferences**：指示视图到其容器视图的配置首选项。

- **持久存储**：存储数据，以便在应用的不同会话中使用。


---
source: https://developer.apple.com/documentation/SwiftUI/Environment-values
crawled: 2025-12-02T17:32:18Z
---

# Environment values

**API Collection**

Share data throughout a view hierarchy using the environment.

## Overview

Views in SwiftUI can react to configuration information that they read from the environment using an [Environment](Environment.zh-Hans.md) property wrapper.



A view inherits its environment from its container view, subject to explicit changes from an [environment(_:_:)](View/environment.zh-Hans.md) view modifier, or by implicit changes from one of the many modifiers that operate on environment values. As a result, you can configure a entire hierarchy of views by modifying the environment of the group’s container.

You can find many built-in environment values in the [EnvironmentValues](EnvironmentValues.zh-Hans.md) structure. You can also create a custom [EnvironmentValues](EnvironmentValues.zh-Hans.md) property by defining a new property in an extension to the environment values structure and applying the [Entry()](Entry.zh-Hans.md) macro to the variable declaration.

## Accessing environment values

- **Environment**: A property wrapper that reads a value from a view’s environment.
- **EnvironmentValues**: A collection of environment values propagated through a view hierarchy.

## Creating custom environment values

- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **EnvironmentKey**: A key for accessing values in the environment.

## Modifying the environment of a view

- **environment(_:)**: Places an observable object in the view’s environment.
- **environment(_:_:)**: Sets the environment value of the specified key path to the given value.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

## Modifying the environment of a scene

- **environment(_:)**: Places an observable object in the scene’s environment.
- **environment(_:_:)**: Sets the environment value of the specified key path to the given value.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

## Data and storage

- **Model data**: Manage the data that your app uses to drive its interface.
- **Preferences**: Indicate configuration preferences from views to their container views.
- **Persistent storage**: Store data for use across sessions of your app.

