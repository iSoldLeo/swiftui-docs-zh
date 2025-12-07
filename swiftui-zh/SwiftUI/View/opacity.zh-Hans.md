--- 来源：https://developer.apple.com/documentation/SwiftUI/View/opacity(_:)

抓取时间：2025-11-30T21:17:39Z

---

# opacity(_:)

**实例方法**

设置此视图的透明度。

## 声明

```swift
nonisolated func opacity(_ opacity: Double) -> some View

```

## 参数

- **opacity**：介于 0（完全透明）和 1（完全不透明）之间的值。

## 返回值

一个设置了此视图透明度的视图。

## 说明

应用透明度来显示位于其他视图后面的视图，或弱化某个视图。

当将 `opacity(_:)` 修饰符应用于已进行过透明度转换的视图时，该修饰符会增强底层透明度转换的效果。

以下示例显示了配置为重叠的黄色和红色矩形。上方黄色矩形的透明度设置为 50%，使得下方矩形被遮挡的部分可见：

```swift
struct Opacity: View {
    var body: some View {
        VStack {
            Color.yellow.frame(width: 100, height: 100, alignment: .center)
                .zIndex(1)
                .opacity(0.5)

            Color.red.frame(width: 100, height: 100, alignment: .center)
                .padding(-40)
        }
    }
}
```

## 隐藏视图

- **hidden()**：无条件隐藏此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/opacity(_:)
crawled: 2025-11-30T21:17:39Z
---

# opacity(_:)

**Instance Method**

Sets the transparency of this view.

## Declaration

```swift
nonisolated func opacity(_ opacity: Double) -> some View

```

## Parameters

- **opacity**: A value between 0 (fully transparent) and 1 (fully opaque).

## Return Value

A view that sets the transparency of this view.

## Discussion

Apply opacity to reveal views that are behind another view or to de-emphasize a view.

When applying the `opacity(_:)` modifier to a view that has already had its opacity transformed, the modifier multiplies the effect of the underlying opacity transformation.

The example below shows yellow and red rectangles configured to overlap. The top yellow rectangle has its opacity set to 50%, allowing the occluded portion of the bottom rectangle to be visible:

```swift
struct Opacity: View {
    var body: some View {
        VStack {
            Color.yellow.frame(width: 100, height: 100, alignment: .center)
                .zIndex(1)
                .opacity(0.5)

            Color.red.frame(width: 100, height: 100, alignment: .center)
                .padding(-40)
        }
    }
}
```



## Hiding views

- **hidden()**: Hides this view unconditionally.

