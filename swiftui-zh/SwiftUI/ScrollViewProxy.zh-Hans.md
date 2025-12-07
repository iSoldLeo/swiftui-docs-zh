---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollViewProxy
抓取时间： 2025-12-02T17:40:13Z
---

# 滚动视图代理

**Structure**

一个代理值，支持在视图层次结构中以编程方式滚动可滚动视图。

### 声明

```swift
struct ScrollViewProxy
```

## 概览

您不能直接创建`ScrollViewProxy` 的实例。相反，您的[ScrollViewReader](ScrollViewReader.zh-Hans.md) 会在`ScrollViewProxy` 的`content` 视图创建器中接收`ScrollViewProxy` 的实例。您可以使用该视图创建器中的操作（如按钮和手势处理程序或 [onChange(of:perform:)](View/onChange_of_perform.zh-Hans.md) 方法）来调用代理的 [scrollTo(_:anchor:)](ScrollViewProxy/scrollTo___anchor.zh-Hans.md) 方法。

## 执行滚动

- **scrollTo(_:anchor:)**：扫描代理包含的所有滚动视图，查找第一个带有标识符`id` 的子视图，然后滚动到该视图。

## 创建滚动视图

- **ScrollView**：可滚动视图。
- **ScrollViewReader**：通过代理滚动到已知子视图，提供编程式滚动的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollViewProxy
crawled: 2025-12-02T17:40:13Z
---

# ScrollViewProxy

**Structure**

A proxy value that supports programmatic scrolling of the scrollable views within a view hierarchy.

## Declaration

```swift
struct ScrollViewProxy
```

## Overview

You don’t create instances of `ScrollViewProxy` directly. Instead, your [ScrollViewReader](ScrollViewReader.zh-Hans.md) receives an instance of `ScrollViewProxy` in its `content` view builder. You use actions within this view builder, such as button and gesture handlers or the [onChange(of:perform:)](View/onChange_of_perform.zh-Hans.md) method, to call the proxy’s [scrollTo(_:anchor:)](ScrollViewProxy/scrollTo___anchor.zh-Hans.md) method.

## Performing scrolling

- **scrollTo(_:anchor:)**: Scans all scroll views contained by the proxy for the first with a child view with identifier `id`, and then scrolls to that view.

## Creating a scroll view

- **ScrollView**: A scrollable view.
- **ScrollViewReader**: A view that provides programmatic scrolling, by working with a proxy to scroll to known child views.

