--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/foregroundColor(_:)

抓取时间：2025-12-01T02:39:33Z

---

# foregroundColor(_:)

**实例方法**

设置此视图显示的文本颜色。

## 声明

```swift
nonisolated func foregroundColor(_ color: Color?) -> Text
```

## 参数

- **color**：显示此文本时使用的颜色。

## 返回值

一个使用您提供的颜色值的文本视图。

## 说明

使用此方法更改文本视图渲染的文本颜色。

例如，您可以分别以红色、绿色和蓝色显示颜色名称：

```swift
HStack {
    Text("Red").foregroundColor(.red)
    Text("Green").foregroundColor(.green)
    Text("Blue").foregroundColor(.blue)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Text/foregroundColor(_:)
crawled: 2025-12-01T02:39:33Z
---

# foregroundColor(_:)

**Instance Method**

Sets the color of the text displayed by this view.

## Declaration

```swift
nonisolated func foregroundColor(_ color: Color?) -> Text
```

## Parameters

- **color**: The color to use when displaying this text.

## Return Value

A text view that uses the color value you supply.

## Discussion

Use this method to change the color of the text rendered by a text view.

For example, you can display the names of the colors red, green, and blue in their respective colors:

```swift
HStack {
    Text("Red").foregroundColor(.red)
    Text("Green").foregroundColor(.green)
    Text("Blue").foregroundColor(.blue)
}
```



