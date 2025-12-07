--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationSizing/sticky(horizontal:vertical:)

抓取时间：2025-12-03T06:02:23Z

---

# sticky(horizontal:vertical:)

**实例方法**

将自身修改为在指定维度上保持粘性——会增长，但不会缩小。

## 声明

```swift
func sticky(horizontal: Bool = false, vertical: Bool = false) -> some PresentationSizing

```

## 参数

- **horizontal**：一个布尔值，指示是否保持水平方向的最大尺寸

- **vertical**：一个布尔值，指示是否保持垂直方向的最大尺寸

## 返回值

修改后的自粘尺寸

## 说明

如果 `sticky` 为 `.vertical`，则当内容增大时，演示文稿可以沿垂直和水平方向扩展，但当内容缩小时，垂直方向不会缩小。

```swift
ContentView()
  .sheet(isPresented: $presentSheet) {
    MyDynamicSheetContent()
      .presentationSizing(
        .form.sticky(horizontal: false, vertical: true))
  }
```

## 创建自定义演示文稿尺寸

- **fitted(horizontal:vertical:)**

- **proposedSize(for:context:)**


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationSizing/sticky(horizontal:vertical:)
crawled: 2025-12-03T06:02:23Z
---

# sticky(horizontal:vertical:)

**Instance Method**

Modifies self to be sticky in the specified dimensions — growing, but not shrinking.

## Declaration

```swift
func sticky(horizontal: Bool = false, vertical: Bool = false) -> some PresentationSizing

```

## Parameters

- **horizontal**: A boolean indicating whether to maintain the largest size horizontally
- **vertical**: A boolean indicating whether to maintain the largest size vertically

## Return Value

A modified version of self sticking to dimensions specified

## Discussion

If `sticky` is `.vertical`, the presentation can grow in the vertical and horizontal dimensions when its content size grows, but will not shrink in the vertical dimension when content size shrinks.

```swift
ContentView()
  .sheet(isPresented: $presentSheet) {
    MyDynamicSheetContent()
      .presentationSizing(
        .form.sticky(horizontal: false, vertical: true))
  }
```



## Creating custom presentation size

- **fitted(horizontal:vertical:)**
- **proposedSize(for:context:)**

