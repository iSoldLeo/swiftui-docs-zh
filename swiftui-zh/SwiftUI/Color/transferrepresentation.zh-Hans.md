---
来源： https://developer.apple.com/documentation/swiftui/color/transferrepresentation
抓取时间：2025-12-04T11:34:00Z
---

# transferRepresentation

**类型属性**

以明确指定的成分值创建的一组颜色--恒定颜色--将按原样传输。

## 声明

```swift
static var transferRepresentation: some TransferRepresentation { get }
```

## 讨论

另一组颜色--标准色（如 `Color.mint`）和语义色（如 `Color.accentColor`）--会根据当前[Environment](../Environment.zh-Hans.md) 在屏幕上以不同的方式呈现。对于传输，它们是根据默认环境解析的，如果拖动或复制的源使用的是非默认环境，则在目的地产生的结果可能会略有不同。


---
source: https://developer.apple.com/documentation/swiftui/color/transferrepresentation
crawled: 2025-12-04T11:34:00Z
---

# transferRepresentation

**Type Property**

One group of colors–constant colors–created with explicitly specified component values are transferred as is.

## Declaration

```swift
static var transferRepresentation: some TransferRepresentation { get }
```

## Discussion

Another group of colors–standard colors, like `Color.mint`, and semantic colors, like `Color.accentColor`–are rendered on screen differently depending on the current [Environment](../Environment.zh-Hans.md). For transferring, they are resolved against the default environment and might produce a slightly different result at the destination if the source of drag or copy uses a non-default environment.

