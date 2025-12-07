---
来源： https://developer.apple.com/documentation/SwiftUI/Glass/clear
抓取时间： 2025-12-03T06:25:41Z
---

# 清除

**类型属性**

玻璃的透明变体。

## 声明

```swift
static var clear: Glass { get }
```

## 讨论

使用透明玻璃时，应在玻璃下方添加调光层或其他处理，以确保内容清晰可读。

例如，您可以在玻璃下方添加透明的黑色，以确保玻璃上方的内容仍然清晰可读。

```swift
Label("Flag", systemImage: "flag.fill")
    .padding()
    .glassEffect(.clear)
    .background(.black.opacity(0.3))
```


---
source: https://developer.apple.com/documentation/SwiftUI/Glass/clear
crawled: 2025-12-03T06:25:41Z
---

# clear

**Type Property**

The clear variant of glass.

## Declaration

```swift
static var clear: Glass { get }
```

## Discussion

When using clear glass, ensure content remains legible by adding a dimming layer or other treatment beneath the glass.

For example, you could add a transparent black color beneath your glass to ensure content remains legible above the glass.

```swift
Label("Flag", systemImage: "flag.fill")
    .padding()
    .glassEffect(.clear)
    .background(.black.opacity(0.3))
```

