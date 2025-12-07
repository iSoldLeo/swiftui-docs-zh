---
来源： https://developer.apple.com/documentation/SwiftUI/SidebarRowSize
抓取时间： 2025-12-02T17:29:39Z
---

# SidebarRowSize

**Enumeration**

侧边栏行的标准尺寸。

## 声明

```swift
enum SidebarRowSize
```

## 概览

在 macOS 上，侧边栏有三种不同的大小：小、中、大。大小主要由当前用户在外观设置中的 "侧边栏图标大小 "控制，并适用于所有应用程序。

在所有其他平台上，唯一支持的侧边栏大小是 `.medium`。

可以使用 `EnvironmentValues.sidebarRowSize`在环境中读取或写入该大小。

## 获取行大小

- **SidebarRowSize.small**：标准 "小 "行尺寸
- **SidebarRowSize.medium**：标准 "中 "行尺寸
- **SidebarRowSize.large**：标准 "大 "行尺寸

## 配置侧边栏

- **sidebarRowSize**：侧边栏行的当前大小。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SidebarRowSize
crawled: 2025-12-02T17:29:39Z
---

# SidebarRowSize

**Enumeration**

The standard sizes of sidebar rows.

## Declaration

```swift
enum SidebarRowSize
```

## Overview

On macOS, sidebar rows have three different sizes: small, medium, and large. The size is primarily controlled by the current users’ “Sidebar Icon Size” in Appearance settings, and applies to all applications.

On all other platforms, the only supported sidebar size is `.medium`.

This size can be read or written in the environment using `EnvironmentValues.sidebarRowSize`.

## Getting row sizes

- **SidebarRowSize.small**: The standard “small” row size
- **SidebarRowSize.medium**: The standard “medium” row size
- **SidebarRowSize.large**: The standard “large” row size

## Configuring the sidebar

- **sidebarRowSize**: The current size of sidebar rows.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

