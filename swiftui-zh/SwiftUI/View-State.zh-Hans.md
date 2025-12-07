---
来源： https://developer.apple.com/documentation/SwiftUI/View-State
抓取时间： 2025-12-02T17:22:19Z
---

# 状态修改器

**API 集合**

访问存储并为子视图提供配置数据。

## 概览

SwiftUI 提供了在应用程序中管理数据的工具。例如，您可以在视图层次结构中的视图之间共享的环境中存储值和对象。任何共享环境的视图（通常是存储项目的视图的所有子视图）都可以访问存储的项目。

有关 SwiftUI 为帮助管理应用程序中的数据而提供的类型的更多信息，请参阅[Model-data](Model-data.zh-Hans.md)。

## 身份

- **tag(_:includeOptional:)**：设置此视图的唯一标记值。
- **id(_:)**：将视图的标识绑定到给定的代理值。
- **equatable()**：当视图的新值与旧值相同时，阻止视图更新其子视图。

### 环境值

- **environment(_:)**：在视图的环境中放置一个可观察对象。
- **environment(_:_:)**：将指定关键路径的环境值设置为给定值。
- **environmentObject(_:)**：向视图的层次结构提供一个可观察对象。
- **transformEnvironment(_:transform:)**：使用给定函数转换指定关键路径的环境值。

## 偏好设置

- **preference(key:value:)**：为给定的偏好设置值。
- **transformPreference(_:_:)**：对偏好值应用转换。
- **anchorPreference(key:value:transform:)**：为指定的偏好键设置一个值，该值是与当前坐标空间绑定的几何体值的函数，允许该值的读者将几何体转换为他们的本地坐标。
- **transformAnchorPreference(key:value:transform:)**：为指定的偏好键设置值，该值是键的当前值和与当前坐标空间绑定的几何体值的函数，允许值的读取者将几何体转换为本地坐标。
- **onPreferenceChange(_:perform:)**：当指定偏好键的值发生变化时，添加一个要执行的操作。
- **backgroundPreferenceValue(_:_:)**：从视图中读取指定的偏好值，并用它生成第二个视图，作为原始视图的背景。
- **backgroundPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好值，并用它生成第二个视图，作为原始视图的背景。
- **overlayPreferenceValue(_:_:)**：从视图中读取指定的偏好值，并用它生成第二个视图，作为原始视图的叠加。
- **overlayPreferenceValue(_:alignment:_:)**：从视图中读取指定的偏好值，并用它生成第二个视图，作为原始视图的叠加应用。

## 默认存储

- **defaultAppStorage(_:)**：视图中包含的 `AppStorage` 所使用的默认存储。

## 配置模型

- **modelContext(_:)**：在此视图的环境中设置模型上下文。
- **modelContainer(_:)**：设置此视图环境中的模型容器和关联模型上下文。
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：在此视图中设置用于存储所提供模型类型的模型容器，必要时创建新容器，并在此视图的环境中为该容器设置模型上下文。

## 提供交互性

- 输入和事件修改器**：为视图提供响应用户输入和系统事件的操作。
- 搜索修饰符**：使人们能够在应用程序中搜索内容。
- 呈现修改器***：为视图定义在指定条件下呈现的其他视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View-State
crawled: 2025-12-02T17:22:19Z
---

# State modifiers

**API Collection**

Access storage and provide child views with configuration data.

## Overview

SwiftUI provides tools for managing data in your app. For example, you can store values and objects in an environment that’s shared among the views in a view hierarchy. Any view that shares the environment — typically all the descendant views of the view that stores the item — can then access the stored item.

For more information about the types that SwiftUI provides to help manage data in your app, see [Model-data](Model-data.zh-Hans.md).

## Identity

- **tag(_:includeOptional:)**: Sets the unique tag value of this view.
- **id(_:)**: Binds a view’s identity to the given proxy value.
- **equatable()**: Prevents the view from updating its child view when its new value is the same as its old value.

## Environment values

- **environment(_:)**: Places an observable object in the view’s environment.
- **environment(_:_:)**: Sets the environment value of the specified key path to the given value.
- **environmentObject(_:)**: Supplies an observable object to a view’s hierarchy.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

## Preferences

- **preference(key:value:)**: Sets a value for the given preference.
- **transformPreference(_:_:)**: Applies a transformation to a preference value.
- **anchorPreference(key:value:transform:)**: Sets a value for the specified preference key, the value is a function of a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.
- **transformAnchorPreference(key:value:transform:)**: Sets a value for the specified preference key, the value is a function of the key’s current value and a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.
- **onPreferenceChange(_:perform:)**: Adds an action to perform when the specified preference key’s value changes.
- **backgroundPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **backgroundPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **overlayPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.
- **overlayPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

## Default storage

- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the view.

## Configuring a model

- **modelContext(_:)**: Sets the model context in this view’s environment.
- **modelContainer(_:)**: Sets the model container and associated model context in this view’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this view for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this view’s environment.

## Providing interactivity

- **Input and event modifiers**: Supply actions for a view to perform in response to user input and system events.
- **Search modifiers**: Enable people to search for content in your app.
- **Presentation modifiers**: Define additional views for the view to present under specified conditions.

