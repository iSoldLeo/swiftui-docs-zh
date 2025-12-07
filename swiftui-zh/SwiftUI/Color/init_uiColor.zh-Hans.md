---
来源： https://developer.apple.com/documentation/SwiftUI/Color/init(uiColor:)
抓取时间： 2025-12-01T10:28:42Z
---

# init(uiColor:)

**Initializer**

从 UIKit 颜色创建颜色。

## 声明

```swift
init(uiColor: UIColor)
```

## 讨论

使用此方法可从[doc://com.apple.documentation/documentation/UIKit/UIColor] 实例创建 SwiftUI 颜色。新颜色保留了原始颜色的适应性。例如，您可以使用 [doc://com.apple.documentation/documentation/UIKit/UIColor/link] 创建一个矩形，查看阴影如何调整以匹配用户的系统设置：

```swift
struct Box: View {
    var body: some View {
        Color(uiColor: .link)
            .frame(width: 200, height: 100)
    }
}
```

当用户打开黑暗模式时，上面定义的`Box` 视图会自动改变外观。将亮色和暗色外观并排放置，可以看到色调上的细微差别：





## 从另一种颜色创建一种颜色

- **init(nsColor:)**：从 AppKit 颜色创建颜色。
- **init(cgColor:)**：从 Core Graphics 颜色创建颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(uiColor:)
crawled: 2025-12-01T10:28:42Z
---

# init(uiColor:)

**Initializer**

Creates a color from a UIKit color.

## Declaration

```swift
init(uiColor: UIColor)
```

## Discussion

Use this method to create a SwiftUI color from a [doc://com.apple.documentation/documentation/UIKit/UIColor] instance. The new color preserves the adaptability of the original. For example, you can create a rectangle using [doc://com.apple.documentation/documentation/UIKit/UIColor/link] to see how the shade adjusts to match the user’s system settings:

```swift
struct Box: View {
    var body: some View {
        Color(uiColor: .link)
            .frame(width: 200, height: 100)
    }
}
```

The `Box` view defined above automatically changes its appearance when the user turns on Dark Mode. With the light and dark appearances placed side by side, you can see the subtle difference in shades:





## Creating a color from another color

- **init(nsColor:)**: Creates a color from an AppKit color.
- **init(cgColor:)**: Creates a color from a Core Graphics color.

