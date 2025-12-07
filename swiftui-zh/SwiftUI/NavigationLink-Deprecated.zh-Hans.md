---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationLink-Deprecated
抓取时间： 2025-12-02T20:58:46Z
---

# 过时的符号

**API 集合**

查看已废弃的导航链接初始化器。

## 概览

有关更新导航符号用法的信息，请参阅 [Migrating-to-New-Navigation-Types](Migrating-to-New-Navigation-Types.zh-Hans.md)。

## 使用视图创建器创建链接

- **init(_:isActive:destination:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有由本地化字符串键生成的文本标签。
- **init(isActive:destination:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(_:tag:selection:destination:)**：**init(_:tag:selection:destination:)**： 创建导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。
- **init(tag:selection:destination:label:)**：创建一个导航链接，当绑定的选择变量等于给定的标签值时，该链接会显示目标视图。

## 为 WatchKit 创建链接

- **init(destinationName:isActive:label:)**：创建一个导航链接，在活动时显示 WatchKit 故事板中的视图。
- **init(destinationName:tag:selection:label:)**：创建一个导航链接，当绑定的选择变量与您提供的值匹配时，该链接将显示 WatchKit 故事板中的视图。
- **init(destinationName:label:)**：创建一个导航链接，从 WatchKit 故事板显示视图。

## 使用视图参数创建链接

- **init(_:destination:isActive:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有一个由本地化字符串键生成的文本标签。
- **init(destination:isActive:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(_:destination:tag:selection:)**：**init(_:destination:tag:selection:)**： 创建导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。
- **init(destination:tag:selection:label:)**：创建一个导航链接，当绑定的选择变量等于给定的标签值时，该链接会显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink-Deprecated
crawled: 2025-12-02T20:58:46Z
---

# Deprecated symbols

**API Collection**

Review deprecated navigation link initializers.

## Overview

For information about updating your use of navigation symbols, see [Migrating-to-New-Navigation-Types](Migrating-to-New-Navigation-Types.zh-Hans.md).

## Creating links with view builders

- **init(_:isActive:destination:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(isActive:destination:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:tag:selection:destination:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.
- **init(tag:selection:destination:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

## Creating links for WatchKit

- **init(destinationName:isActive:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard when active.
- **init(destinationName:tag:selection:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard when a bound selection variable matches a value you provide.
- **init(destinationName:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard.

## Creating links with view arguments

- **init(_:destination:isActive:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(destination:isActive:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:destination:tag:selection:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.
- **init(destination:tag:selection:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

