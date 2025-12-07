--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/customAttribute(_:)

抓取时间：2025-12-02T21:48:46Z

---

# customAttribute(_:)

**实例方法**

向文本视图添加自定义属性。

## 声明

```swift
func customAttribute<T>(_ value: T) -> Text where T : TextAttribute
```

## 参数

- **value**：要附加的属性。

## 返回值

附加了 `value` 的文本视图版本。

## 说明

每个文本视图只能附加一个相同类型的属性，内部属性优先。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/customAttribute(_:)
crawled: 2025-12-02T21:48:46Z
---

# customAttribute(_:)

**Instance Method**

Adds a custom attribute to the text view.

## Declaration

```swift
func customAttribute<T>(_ value: T) -> Text where T : TextAttribute
```

## Parameters

- **value**: The attribute to attach.

## Return Value

A version of the text view with `value` attached.

## Discussion

Only one attribute of each type may be attached to each text view, with inner attributes taking precedence.

