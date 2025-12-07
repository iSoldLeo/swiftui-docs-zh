---
来源：https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(sectionID:)
抓取时间： 2025-12-02T21:00:03Z
---

# subscript(sectionID:)

**实例下标**

节的自定义标识符标识的节的子节的自定义。

## 声明

```swift
subscript(sectionID id: String) -> [String]? { get }
```

## 概览

可以通过下标选项卡章节的 id 来读取章节顺序：

```swift
let order = customization[sectionID: "com.myApp.categories"]
```

使用`customizationID(_:)`修饰符，可将标识符与`Tab` 或`TabSection` 关联。

```swift
TabSection("Categories") {
    Tab("Climate", systemImage: "fan") {
        ClimateView()
    }
    .customizationID("com.myApp.climate")

    Tab("Lights", systemImage: "lightbulb") {
        LightsView()
    }
    .customizationID("com.myApp.lights")
}
.customizationID("com.myApp.categories")
```

如果 ID 未与节段相关联或节段未被自定义，则返回`nil` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/subscript(sectionID:)
crawled: 2025-12-02T21:00:03Z
---

# subscript(sectionID:)

**Instance Subscript**

The customization for a section’s children, identified by the section’s customization identifier.

## Declaration

```swift
subscript(sectionID id: String) -> [String]? { get }
```

## Overview

Section order can be read by subscripting with the tab section’s id:

```swift
let order = customization[sectionID: "com.myApp.categories"]
```

Identifiers can be associated with a `Tab` or `TabSection` using the `customizationID(_:)` modifier.

```swift
TabSection("Categories") {
    Tab("Climate", systemImage: "fan") {
        ClimateView()
    }
    .customizationID("com.myApp.climate")

    Tab("Lights", systemImage: "lightbulb") {
        LightsView()
    }
    .customizationID("com.myApp.lights")
}
.customizationID("com.myApp.categories")
```

If the ID isn’t associated with a section or the section has not been customized, a default value of `nil` is returned.

