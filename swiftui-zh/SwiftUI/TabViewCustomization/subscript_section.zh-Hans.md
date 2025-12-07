---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(部分：)
抓取时间： 2025-12-01T00:44:03Z
---

# subscript(section:)

**实例下标**

小节的定制，由其定制标识符标识。

## 声明

```swift
subscript(section id: String) -> TabViewCustomization.SectionCustomization { get set }
```

## 概览

通过下标选项卡部分的 id，可以读取部分选项卡顺序：

```swift
let order = customization[section: "com.myApp.categories"].tabOrder
```

要重置单个章节的顺序，请使用 [resetTabOrder()](SectionCustomization/resetTabOrder.zh-Hans.md)。要重置所有章节的顺序，请使用 [resetSectionOrder()](resetSectionOrder.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(section:)
crawled: 2025-12-01T00:44:03Z
---

# subscript(section:)

**Instance Subscript**

The customization of the section, identified by its customization identifier.

## Declaration

```swift
subscript(section id: String) -> TabViewCustomization.SectionCustomization { get set }
```

## Overview

Section tab order can be read by subscripting with the tab section’s id:

```swift
let order = customization[section: "com.myApp.categories"].tabOrder
```

To reset the order of an individual section, use [resetTabOrder()](SectionCustomization/resetTabOrder.zh-Hans.md). To reset the order of all sections, use [resetSectionOrder()](resetSectionOrder.zh-Hans.md).

