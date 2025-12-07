--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tipAnchor(_:)

抓取时间：2025-11-30T21:11:13Z

---

# tipAnchor(_:)

**实例方法**

设置指定提示锚点的值，用于将提示视图锚定到视图的 `.bounds` 位置。

## 声明

```swift
nonisolated func tipAnchor<AnchorID>(_ id: AnchorID) -> some View where AnchorID : Hashable, AnchorID : Sendable

```

## 参数

- **id**：被锚定视图的标识符。

## 返回值

写入指定键的视图新版本。

## 说明

使用此修饰符指定箭头指向的锚点视图。

```swift
struct TrailRow: View {
    let trail: Trail

    var body: some View {
        HStack {
            Text(trail.name)

            Button(action: trail.favorite) {
                Image(systemName: "star")
            }
            .tipAnchor("FavoriteTrailTipAnchor")
        }

        TipView(FavoriteTrailTip(), anchorID: "FavoriteTrailTipAnchor")
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/tipAnchor(_:)
crawled: 2025-11-30T21:11:13Z
---

# tipAnchor(_:)

**Instance Method**

Sets a value for the specified tip anchor to be used to anchor a tip view to the `.bounds` of the view.

## Declaration

```swift
nonisolated func tipAnchor<AnchorID>(_ id: AnchorID) -> some View where AnchorID : Hashable, AnchorID : Sendable

```

## Parameters

- **id**: The anchored view’s identifier.

## Return Value

A new version of the view that writes to the key.

## Discussion

Use this modifier to specify an anchor view for a `TipView`’s arrow to point towards.

```swift
struct TrailRow: View {
    let trail: Trail

    var body: some View {
        HStack {
            Text(trail.name)

            Button(action: trail.favorite) {
                Image(systemName: "star")
            }
            .tipAnchor("FavoriteTrailTipAnchor")
        }

        TipView(FavoriteTrailTip(), anchorID: "FavoriteTrailTipAnchor")
    }
}
```

