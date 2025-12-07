--- 来源：https://developer.apple.com/documentation/swiftui/presentationsizingroot
抓取时间：2025-12-04T13:08:31Z

---

# PresentationSizingRoot

**Structure**

为演示文稿提供具有已定义演示大小的视图代理。

## 声明

```swift
struct PresentationSizingRoot
```

## 实例方法

- **sizeThatFits(_:)**：向子视图请求其大小。

## 调整演示大小

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸类。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类。

- **PresentationAdaptation**：将演示文稿调整为不同尺寸类的策略。

- **presentationSizing(_:)**：设置包含演示文稿的窗口大小。

- **PresentationSizing**：定义演示文稿内容的大小以及演示文稿大小如何随内容大小变化而调整的类型。

- **PresentationSizingContext**：关于演示文稿的上下文信息。


---
source: https://developer.apple.com/documentation/swiftui/presentationsizingroot
crawled: 2025-12-04T13:08:31Z
---

# PresentationSizingRoot

**Structure**

A proxy to a view provided to the presentation with a defined presentation size.

## Declaration

```swift
struct PresentationSizingRoot
```

## Instance Methods

- **sizeThatFits(_:)**: Asks the subview for its size.

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingContext**: Contextual information about a presentation.

