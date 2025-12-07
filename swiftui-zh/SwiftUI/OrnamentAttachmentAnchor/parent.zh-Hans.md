--- 来源：https://developer.apple.com/documentation/SwiftUI/OrnamentAttachmentAnchor/parent(_:)

抓取时间：2025-12-03T06:05:22Z

---

# parent(_:)

**类型方法**

装饰物的锚点，以相对于其父对象的 3D 单位点表示。

## 声明

```swift
static func parent(_ anchor: UnitPoint3D) -> OrnamentAttachmentAnchor
```

## 讨论

父对象取决于装饰物修饰符的位置。当在另一个装饰物上下文中使用时，该装饰物即为父对象。否则，父对象为场景本身。


---
source: https://developer.apple.com/documentation/SwiftUI/OrnamentAttachmentAnchor/parent(_:)
crawled: 2025-12-03T06:05:22Z
---

# parent(_:)

**Type Method**

The anchor point for the ornament expressed as a 3D unit point relative to its parent.

## Declaration

```swift
static func parent(_ anchor: UnitPoint3D) -> OrnamentAttachmentAnchor
```

## Discussion

The parent depends on where the ornament modifier is placed. When used inside another ornament context, that ornament is the parent. Otherwise, it’s the Scene itself.

