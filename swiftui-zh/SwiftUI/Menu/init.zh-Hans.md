--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(_:)

抓取时间：2025-12-01T10:32:06Z

---

# init(_:)

**Initializer**

根据样式配置创建菜单。

## 声明

```swift
nonisolated init(_ configuration: MenuStyleConfiguration)
```

## 讨论

在 [MenuStyle](../MenuStyle.zh-Hans.md) 实例的 [makeBody(configuration:)](../MenuStyle/makeBody_configuration.zh-Hans.md) 方法中使用此初始化器，即可创建要设置样式的菜单实例。这对于修改当前菜单样式的自定义菜单样式非常有用。

例如，以下代码创建了一个新的自定义样式，该样式会在当前菜单样式周围添加红色边框：

```swift
struct RedBorderMenuStyle: MenuStyle {
    func makeBody(configuration: Configuration) -> some View {
        Menu(configuration)
            .border(Color.red)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(_:)
crawled: 2025-12-01T10:32:06Z
---

# init(_:)

**Initializer**

Creates a menu based on a style configuration.

## Declaration

```swift
nonisolated init(_ configuration: MenuStyleConfiguration)
```

## Discussion

Use this initializer within the [makeBody(configuration:)](../MenuStyle/makeBody_configuration.zh-Hans.md) method of a [MenuStyle](../MenuStyle.zh-Hans.md) instance to create an instance of the menu being styled. This is useful for custom menu styles that modify the current menu style.

For example, the following code creates a new, custom style that adds a red border around the current menu style:

```swift
struct RedBorderMenuStyle: MenuStyle {
    func makeBody(configuration: Configuration) -> some View {
        Menu(configuration)
            .border(Color.red)
    }
}
```

