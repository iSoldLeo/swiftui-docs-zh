---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/buttonSizing
抓取时间： 2025-12-03T06:07:39Z
---

# 按钮大小

**实例属性**

视图层次结构中按钮的首选大小行为。

## 声明

```swift
var buttonSizing: ButtonSizing { get }
```

## 讨论

视图可以使用指定的按钮尺寸来确定它们在父视图的建议尺寸中选择的主轴尺寸。

使用[buttonSizing(_:)](../View/buttonSizing.zh-Hans.md) 在环境中设置首选大小行为。许多显示为按钮的内置控件都会适应该环境值。您也可以在自己的视图和样式中读取环境值，以适应首选大小。

```swift
struct CustomButtonStyle: ButtonStyle {
    @Environment(\.buttonSizing) private var buttonSizing

    private var maxWidth: CGFloat {
        switch buttonSizing {
        case .flexible: .infinity
        case .fitted, _: nil
        }
    }

    func makeBody(configuration: Configuration) -> some View {
        configuration.content
            .frame(maxWidth: maxWidth)
            .background(.tint, in: Capsule())
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/buttonSizing
crawled: 2025-12-03T06:07:39Z
---

# buttonSizing

**Instance Property**

The preferred sizing behavior of buttons in the view hierarchy.

## Declaration

```swift
var buttonSizing: ButtonSizing { get }
```

## Discussion

Views may use the specified button sizing when determining the size they choose to be in their primary axis within their parent view’s proposed size.

Use [buttonSizing(_:)](../View/buttonSizing.zh-Hans.md) to set the preferred sizing behavior in the environment. Many built-in controls that display as a button adapt to this environment value. You can read the environment value in your own views and styles as well to adapt to the preferred sizing.

```swift
struct CustomButtonStyle: ButtonStyle {
    @Environment(\.buttonSizing) private var buttonSizing

    private var maxWidth: CGFloat {
        switch buttonSizing {
        case .flexible: .infinity
        case .fitted, _: nil
        }
    }

    func makeBody(configuration: Configuration) -> some View {
        configuration.content
            .frame(maxWidth: maxWidth)
            .background(.tint, in: Capsule())
    }
}
```

