--- 来源：https://developer.apple.com/documentation/SwiftUI/WidgetBundle/body-swift.property

抓取时间：2025-12-02T17:49:01Z

---

# body

**实例属性**

声明应用支持的组件组。

## 声明

```swift
@WidgetBundleBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 说明

此属性中组件的排列顺序决定了用户添加组件时组件的显示顺序。以下示例展示了如何使用组件包构建器定义一个 body，首先显示游戏状态组件，然后显示角色详情组件：

```swift
@main
struct GameWidgets: WidgetBundle {
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## 实现组件包

- **Body**：表示组件包内容的组件类型。

- **WidgetBundleBuilder**：用于构建组件包主体的自定义属性。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundle/body-swift.property
crawled: 2025-12-02T17:49:01Z
---

# body

**Instance Property**

Declares the group of widgets that an app supports.

## Declaration

```swift
@WidgetBundleBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

The order that the widgets appear in this property determines the order they are shown to the user when adding a widget. The following example shows how to use a widget bundle builder to define a body showing a game status widget first and a character detail widget second:

```swift
@main
struct GameWidgets: WidgetBundle {
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## Implementing a widget bundle

- **Body**: The type of widget that represents the content of the bundle.
- **WidgetBundleBuilder**: A custom attribute that constructs a widget bundle’s body.

