--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(_:alignment:)

抓取时间：2025-12-03T05:35:29Z

---

# background(_:alignment:)

**实例方法**

将指定的视图置于当前视图的后面。

## 声明

```swift
nonisolated func background<Background>(_ background: Background, alignment: Alignment = .center) -> some View where Background : View

```

## 参数

- **background**：要绘制在当前视图后面的视图。

- **alignment**：用于定位背景视图的对齐方式，默认值为 [center](../Alignment/center.zh-Hans.md)。

## 说明

当需要将一个视图置于另一个视图后面时，可以使用 `background(_:alignment:)`，背景视图可以选择性地与最前面视图的指定边缘对齐。

以下示例创建两个视图：`Frontmost` 视图和 `DiamondBackground` 视图。`Frontmost` 视图使用 `DiamondBackground` 视图作为 `Frontmost` 视图的 [VStack](../VStack.zh-Hans.md) 内图像元素的背景。

```swift
struct DiamondBackground: View {
    var body: some View {
        VStack {
            Rectangle()
                .fill(Color.gray)
                .frame(width: 250, height: 250, alignment: .center)
                .rotationEffect(.degrees(45.0))
        }
    }
}

struct Frontmost: View {
    var body: some View {
        VStack {
            Image(systemName: "folder")
                .font(.system(size: 128, weight: .ultraLight))
                .background(DiamondBackground())
        }
    }
}
```

## 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。

- **listRowPlatterColor(_:)**：设置当此视图位于列表中时，系统应用于行背景的颜色。

- **overlay(_:alignment:)**：在此视图前面叠加一个辅助视图。

- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。

- **complicationForeground()**：将此视图提升为复杂视图中的前景。


---
source: https://developer.apple.com/documentation/SwiftUI/View/background(_:alignment:)
crawled: 2025-12-03T05:35:29Z
---

# background(_:alignment:)

**Instance Method**

Layers the given view behind this view.

## Declaration

```swift
nonisolated func background<Background>(_ background: Background, alignment: Alignment = .center) -> some View where Background : View

```

## Parameters

- **background**: The view to draw behind this view.
- **alignment**: The alignment with a default value of [center](../Alignment/center.zh-Hans.md) that you use to position the background view.

## Discussion

Use `background(_:alignment:)` when you need to place one view behind another, with the background view optionally aligned with a specified edge of the frontmost view.

The example below creates two views: the `Frontmost` view, and the `DiamondBackground` view. The `Frontmost` view uses the `DiamondBackground` view for the background of the image element inside the `Frontmost` view’s [VStack](../VStack.zh-Hans.md).

```swift
struct DiamondBackground: View {
    var body: some View {
        VStack {
            Rectangle()
                .fill(Color.gray)
                .frame(width: 250, height: 250, alignment: .center)
                .rotationEffect(.degrees(45.0))
        }
    }
}

struct Frontmost: View {
    var body: some View {
        VStack {
            Image(systemName: "folder")
                .font(.system(size: 128, weight: .ultraLight))
                .background(DiamondBackground())
        }
    }
}
```



## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

