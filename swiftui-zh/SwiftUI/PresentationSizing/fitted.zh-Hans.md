---

来源：https://developer.apple.com/documentation/SwiftUI/PresentationSizing/fitted

抓取时间：2025-12-03T06:02:08Z

---

# fitted

**类型属性**

演示文稿的尺寸由内容的理想尺寸决定。

## 声明

```swift
static var fitted: FittedPresentationSizing { get }
```

## 讨论

在 macOS 上，使用 `.fitted` 尺寸的演示文稿默认可由用户调整大小。因此，最佳实践是使用 `frame` 修饰符定义演示文稿框架，指定固定框架或最小/最大边界。如果指定 [fixedSize()](../View/fixedSize.zh-Hans.md) 或为内容指定固定尺寸的框架，则工作表将无法由用户调整大小。

```swift
@State private var present = true

ContentView().sheet(isPresented: $present) {
  ScrollView {
    LazyVGrid(columns: columns) {
      ForEach(0x1f600...0x1f679, id: \.self) { value in
        Text(String(format: "%x", value))
        Text(emoji(value))
          .font(.largeTitle)
        }
      }
  }
  .presentationSizing(.fitted)
  .frame(
    minWidth: 200, idealWidth: 300, maxWidth: 500,
    minHeight: 100, maxHeight: 600)
}
```

要创建适合水平或垂直方向尺寸的视图，请参阅 [fitted(horizontal:vertical:)](fitted_horizontal_vertical.zh-Hans.md)。

## 获取内置演示尺寸

- **automatic**：默认演示尺寸，适用于平台。

- **form**：此尺寸适用于表单，宽度略小于 `.page`。

- **page**：此尺寸大致相当于一张纸的大小，适用于信息或排版内容。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationSizing/fitted
crawled: 2025-12-03T06:02:08Z
---

# fitted

**Type Property**

The presentation sizing is dictated by the ideal size of the content

## Declaration

```swift
static var fitted: FittedPresentationSizing { get }
```

## Discussion

On macOS, presentations with `.fitted` sizing are user-resizable by default. Because of this, is best practice to define a presentation frame with any of the `frame` modifiers, either specifying a fixed frame or minimum/maximum bounds. If you specify a [fixedSize()](../View/fixedSize.zh-Hans.md) or a frame with fixed dimensions on the content, the sheet will not be user resizable.

```swift
@State private var present = true

ContentView().sheet(isPresented: $present) {
  ScrollView {
    LazyVGrid(columns: columns) {
      ForEach(0x1f600...0x1f679, id: \.self) { value in
        Text(String(format: "%x", value))
        Text(emoji(value))
          .font(.largeTitle)
        }
      }
  }
  .presentationSizing(.fitted)
  .frame(
    minWidth: 200, idealWidth: 300, maxWidth: 500,
    minHeight: 100, maxHeight: 600)
}
```

To create a view that fits the view’s size in either the horizontal or vertical dimensions, see [fitted(horizontal:vertical:)](fitted_horizontal_vertical.zh-Hans.md).

## Getting built-in presentation size

- **automatic**: The default presentation sizing, appropriate for the platform.
- **form**: The size is appropriate for forms and slightly less wide than`.page`
- **page**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

