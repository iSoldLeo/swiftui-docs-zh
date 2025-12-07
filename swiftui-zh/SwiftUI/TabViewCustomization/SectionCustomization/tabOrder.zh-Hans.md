---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/SectionCustomization/tabOrder
抓取时间： 2025-12-03T17:20:56Z
---

# 标签顺序

**实例属性**

一节中标签的自定义顺序，由自定义标识符标识。

## 声明

```swift
var tabOrder: [String]? { get }
```

## 讨论

使用`Tab`修饰符，标识符可与`Tab`或`TabSection`相关联。

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

通过使用标签部分的 id 作为自定义的下标，可以读取部分标签顺序：

```swift
let order = customization[section: "com.myApp.categories"].tabOrder
```

如果部分已自定义，则返回部分中所有选项卡的当前顺序，包括未自定义的选项卡。如果未自定义节或标识符与节不对应，则顺序为空，表示选项卡顺序与创建器的顺序一致。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/SectionCustomization/tabOrder
crawled: 2025-12-03T17:20:56Z
---

# tabOrder

**Instance Property**

The order customization for the tabs in a section, identified by customization identifier.

## Declaration

```swift
var tabOrder: [String]? { get }
```

## Discussion

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

Section tab order can be read by subscripting the customization with the tab section’s id:

```swift
let order = customization[section: "com.myApp.categories"].tabOrder
```

If the section has been customized, this returns the current order for all the tabs in the section, including tabs that have not been customized. If the section has not been customized or the identifier does not correspond to a section, the order will be nil to indicate the tab order matches that of the builder.

