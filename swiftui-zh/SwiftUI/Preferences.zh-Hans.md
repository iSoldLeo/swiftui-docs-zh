--- 来源：https://developer.apple.com/documentation/SwiftUI/Preferences
抓取时间：2025-12-02T17:32:19Z

---

# 偏好设置

**API 集合**

将视图的配置偏好设置传递给其容器视图。

## 概述

与使用环境来配置视图的子视图不同，偏好设置用于将配置信息从子视图发送到其容器。但是，与配置信息从视图层级结构中一个容器向下传递到多个子视图不同，单个容器需要协调来自其多个子视图的潜在冲突偏好设置。

当您使用 [PreferenceKey](PreferenceKey.zh-Hans.md) 协议定义自定义偏好设置时，您需要指定如何合并来自多个子视图的偏好设置。然后，您可以使用 [preference(key:value:)](View/preference_key_value.zh-Hans.md) 视图修饰符为视图上的偏好设置设置值。许多内置修改器，例如 [navigationTitle(_:)](View/navigationTitle.zh-Hans.md)，都依赖于首选项向其容器发送配置信息。

## 设置首选项

- **preference(key:value:)**：设置给定首选项的值。

- **transformPreference(_:_:)**：对首选项值应用变换。

## 创建自定义首选项

- **PreferenceKey**：视图生成的命名值。

## 基于几何体设置首选项

- **anchorPreference(key:value:transform:)**：设置指定首选项键的值，该值是与当前坐标空间关联的几何体的函数，允许读取该值的用户将几何体转换为其局部坐标。

- **transformAnchorPreference(key:value:transform:)**：设置指定首选项键的值，该值是键的当前值和与当前坐标空间关联的几何值的函数，允许读取该值的用户将几何值转换为其本地坐标。

## 响应首选项更改

- **onPreferenceChange(_:perform:)**：添加一个操作，当指定首选项键的值发生更改时执行该操作。

## 根据首选项生成背景和叠加层

- **backgroundPreferenceValue(_:_:)**：从视图中读取指定的首选项值，并使用该值生成第二个视图，该视图将作为原始视图的背景。

- **backgroundPreferenceValue(_:alignment:_:)**：从视图中读取指定的首选项值，并使用该值生成第二个视图，该视图将作为原始视图的背景。

- **overlayPreferenceValue(_:_:)**：从视图中读取指定的首选项值，并使用该值生成第二个视图，该视图将作为叠加层应用到原始视图上。

- **overlayPreferenceValue(_:alignment:_:)**：从视图中读取指定的首选项值，并使用该值生成第二个视图，该视图将作为叠加层应用到原始视图上。

## 数据和存储

- **模型数据**：管理应用用于驱动其界面的数据。

- **环境值**：使用环境在视图层次结构中共享数据。

- **持久存储**：存储数据以供应用在不同会话之间使用。


---
source: https://developer.apple.com/documentation/SwiftUI/Preferences
crawled: 2025-12-02T17:32:19Z
---

# Preferences

**API Collection**

Indicate configuration preferences from views to their container views.

## Overview

Whereas you use the environment to configure the subviews of a view, you use preferences to send configuration information from subviews toward their container. However, unlike configuration information that flows down a view hierarchy from one container to many subviews, a single container needs to reconcile potentially conflicting preferences flowing up from its many subviews.



When you use the [PreferenceKey](PreferenceKey.zh-Hans.md) protocol to define a custom preference, you indicate how to merge preferences from multiple subviews. You can then set a value for the preference on a view using the [preference(key:value:)](View/preference_key_value.zh-Hans.md) view modifier. Many built-in modifiers, like [navigationTitle(_:)](View/navigationTitle.zh-Hans.md), rely on preferences to send configuration information to their container.

## Setting preferences

- **preference(key:value:)**: Sets a value for the given preference.
- **transformPreference(_:_:)**: Applies a transformation to a preference value.

## Creating custom preferences

- **PreferenceKey**: A named value produced by a view.

## Setting preferences based on geometry

- **anchorPreference(key:value:transform:)**: Sets a value for the specified preference key, the value is a function of a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.
- **transformAnchorPreference(key:value:transform:)**: Sets a value for the specified preference key, the value is a function of the key’s current value and a geometry value tied to the current coordinate space, allowing readers of the value to convert the geometry to their local coordinates.

## Responding to changes in preferences

- **onPreferenceChange(_:perform:)**: Adds an action to perform when the specified preference key’s value changes.

## Generating backgrounds and overlays from preferences

- **backgroundPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **backgroundPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as the background of the original view.
- **overlayPreferenceValue(_:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.
- **overlayPreferenceValue(_:alignment:_:)**: Reads the specified preference value from the view, using it to produce a second view that is applied as an overlay to the original view.

## Data and storage

- **Model data**: Manage the data that your app uses to drive its interface.
- **Environment values**: Share data throughout a view hierarchy using the environment.
- **Persistent storage**: Store data for use across sessions of your app.

