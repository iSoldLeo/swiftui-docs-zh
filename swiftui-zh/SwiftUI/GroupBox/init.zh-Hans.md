--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupBox/init(_:)

抓取时间：2025-12-01T10:31:10Z

---

# init(_:)

**Initializer**

根据样式配置创建分组框。

## 声明

```swift
nonisolated init(_ configuration: GroupBoxStyleConfiguration)
```

## 参数

- **configuration**：要创建的分组框实例的属性。

## 说明

在 [GroupBoxStyle](../GroupBoxStyle.zh-Hans.md) 实例的 [makeBody(configuration:)](../GroupBoxStyle/makeBody_configuration.zh-Hans.md) 方法中使用此初始化器，可以创建一个带有自定义样式的分组框，同时保留其现有样式。

以下示例在分组框周围添加粉色边框，而不会覆盖其现有样式：

```swift
struct PinkBorderGroupBoxStyle: GroupBoxStyle {
    func makeBody(configuration: Configuration) -> some View {
        GroupBox(configuration)
            .border(Color.pink)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBox/init(_:)
crawled: 2025-12-01T10:31:10Z
---

# init(_:)

**Initializer**

Creates a group box based on a style configuration.

## Declaration

```swift
nonisolated init(_ configuration: GroupBoxStyleConfiguration)
```

## Parameters

- **configuration**: The properties of the group box instance being created.

## Discussion

Use this initializer within the [makeBody(configuration:)](../GroupBoxStyle/makeBody_configuration.zh-Hans.md) method of a [GroupBoxStyle](../GroupBoxStyle.zh-Hans.md) instance to create a styled group box, with customizations, while preserving its existing style.

The following example adds a pink border around the group box, without overriding its current style:

```swift
struct PinkBorderGroupBoxStyle: GroupBoxStyle {
    func makeBody(configuration: Configuration) -> some View {
        GroupBox(configuration)
            .border(Color.pink)
    }
}
```

