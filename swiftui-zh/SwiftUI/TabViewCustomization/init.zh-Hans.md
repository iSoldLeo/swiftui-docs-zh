---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/init()
抓取时间：2025-12-02T20:59:58Z
---

# init()

**Initializer**

创建一个空的自定义标签页边栏。

## 声明

```swift
init()
```

## 讨论

要在标签视图中设置此自定义功能，请使用 [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md) 修改器。

如果自定义设置为空，则选项卡将按照默认的创建器可见性显示，各部分将按照选项卡视图的选项卡创建器中声明的顺序排列。

您可以通过为选项卡附加 [defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) 来指定选项卡在选项卡栏和侧边栏中的默认可见性。

您可以通过在创建器中更改顺序来更改默认的部分顺序。如果已有持久化定制，则在更改顺序时调用[resetTabOrder()](SectionCustomization/resetTabOrder.zh-Hans.md)，重置顺序。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization/init()
crawled: 2025-12-02T20:59:58Z
---

# init()

**Initializer**

Creates an empty tab sidebar customization.

## Declaration

```swift
init()
```

## Discussion

To set this customization on a tab view, use the [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md) modifier.

With an empty customization, tabs will be visible according to the default builder visibilities, and sections will be ordered in the order declared in the tab view’s tab builder.

You can specify a default visibility for the tab in the tab bar and sidebar by attaching [defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) to the tab.

You can change the default section order by changing the order in the builder. If there’s an existing persisted customization, reset the order by calling [resetTabOrder()](SectionCustomization/resetTabOrder.zh-Hans.md) when you change the order.

