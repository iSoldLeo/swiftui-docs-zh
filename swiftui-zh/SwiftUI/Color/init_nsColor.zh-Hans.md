---
来源： https://developer.apple.com/documentation/SwiftUI/Color/init(nsColor:)
抓取时间： 2025-12-03T05:39:35Z
---

# init(nsColor:)

**Initializer**

从 AppKit 颜色创建颜色。

## 声明

```swift
nonisolated init(nsColor: NSColor)
```

## 讨论

使用此方法可从[doc://com.apple.documentation/documentation/AppKit/NSColor] 实例创建 SwiftUI 颜色。新颜色保留了原始颜色的适应性。例如，您可以使用 [doc://com.apple.documentation/documentation/AppKit/NSColor/linkColor] 创建一个矩形，查看阴影如何调整以匹配用户的系统设置：

```swift
struct Box: View {
    var body: some View {
        Color(nsColor: .linkColor)
            .frame(width: 200, height: 100)
    }
}
```

当用户打开黑暗模式时，上面定义的`Box` 视图会自动改变外观。将亮色和暗色外观并排放置，可以看到色调上的细微差别：





## 从另一种颜色创建一种颜色

- **init(uiColor:)**：从 UIKit 颜色创建颜色。
- **init(cgColor:)**：从 Core Graphics 颜色创建颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(nsColor:)
crawled: 2025-12-03T05:39:35Z
---

# init(nsColor:)

**Initializer**

Creates a color from an AppKit color.

## Declaration

```swift
nonisolated init(nsColor: NSColor)
```

## Discussion

Use this method to create a SwiftUI color from an [doc://com.apple.documentation/documentation/AppKit/NSColor] instance. The new color preserves the adaptability of the original. For example, you can create a rectangle using [doc://com.apple.documentation/documentation/AppKit/NSColor/linkColor] to see how the shade adjusts to match the user’s system settings:

```swift
struct Box: View {
    var body: some View {
        Color(nsColor: .linkColor)
            .frame(width: 200, height: 100)
    }
}
```

The `Box` view defined above automatically changes its appearance when the user turns on Dark Mode. With the light and dark appearances placed side by side, you can see the subtle difference in shades:





## Creating a color from another color

- **init(uiColor:)**: Creates a color from a UIKit color.
- **init(cgColor:)**: Creates a color from a Core Graphics color.

