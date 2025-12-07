--- 来源：https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyleConfiguration/role

抓取时间：2025-12-03T06:09:14Z

---

# role

**实例属性**

一个可选的语义角色，用于描述按钮的用途。

## 声明

```swift
let role: ButtonRole?
```

## 说明

值为 `nil` 表示按钮未分配角色。如果按钮已分配角色，则可以使用该角色来调整按钮的外观。以下示例展示了一种自定义样式，当角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 时使用粗体文本，当角色为 [destructive](../ButtonRole/destructive.zh-Hans.md) 时使用粗体文本，其他情况下不添加任何特殊样式：

```swift
struct MyButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .onTapGesture {
                configuration.trigger()
            }
            .font(
                configuration.role == .cancel ? .title2.bold() : .title2)
            .foregroundColor(
                configuration.role == .destructive ? Color.red : nil)
    }
}
```

您可以创建一个按钮来查看此样式的效果：

```swift
VStack(spacing: 20) {
    Button("Cancel", role: .cancel) {}
    Button("Delete", role: .destructive) {}
    Button("Continue") {}
}
.buttonStyle(MyButtonStyle())
```


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyleConfiguration/role
crawled: 2025-12-03T06:09:14Z
---

# role

**Instance Property**

An optional semantic role describing the button’s purpose.

## Declaration

```swift
let role: ButtonRole?
```

## Discussion

A value of `nil` means that the Button has no assigned role. If the button does have a role, use it to make adjustments to the button’s appearance. The following example shows a custom style that uses bold text when the role is [cancel](../ButtonRole/cancel.zh-Hans.md), [red](../ShapeStyle/red.zh-Hans.md) text when the role is [destructive](../ButtonRole/destructive.zh-Hans.md), and adds no special styling otherwise:

```swift
struct MyButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .onTapGesture {
                configuration.trigger()
            }
            .font(
                configuration.role == .cancel ? .title2.bold() : .title2)
            .foregroundColor(
                configuration.role == .destructive ? Color.red : nil)
    }
}
```

You can create one of each button using this style to see the effect:

```swift
VStack(spacing: 20) {
    Button("Cancel", role: .cancel) {}
    Button("Delete", role: .destructive) {}
    Button("Continue") {}
}
.buttonStyle(MyButtonStyle())
```



