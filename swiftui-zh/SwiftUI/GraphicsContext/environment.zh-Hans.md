---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/environment
抓取时间： 2025-12-02T20:58:31Z
---

# 环境

**实例属性**

与图形上下文相关联的环境。

## 声明

```swift
var environment: EnvironmentValues { get }
```

## 讨论

SwiftUI 最初会将其设置为上下文的外层视图的环境。上下文使用环境中的显示分辨率和配色方案等值来解析[Image](../Image.zh-Hans.md) 和[Color](../Color.zh-Hans.md) 等类型。您还可以为自己的目的访问存储在环境中的值。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/environment
crawled: 2025-12-02T20:58:31Z
---

# environment

**Instance Property**

The environment associated with the graphics context.

## Declaration

```swift
var environment: EnvironmentValues { get }
```

## Discussion

SwiftUI initially sets this to the environment of the context’s enclosing view. The context uses values like display resolution and the color scheme from the environment to resolve types like [Image](../Image.zh-Hans.md) and [Color](../Color.zh-Hans.md). You can also access values stored in the environment for your own purposes.

