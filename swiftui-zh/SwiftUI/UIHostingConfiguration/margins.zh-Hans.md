---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/margins(_:_:)
抓取时间： 2025-12-03T07:00:27Z
---

# margins(_:_:)

**实例方法**

设置配置内容的边距。

## 声明

```swift
func margins(_ edges: Edge.Set = .all, _ insets: EdgeInsets) -> UIHostingConfiguration<Content, Background>
```

## 参数

- **edges**：要应用嵌入的边缘。未指定的边缘将使用系统默认值。默认值为 [all](../Edge/Set/all.zh-Hans.md)。
- **insets**：要应用的镶边。

## 讨论

使用此修改器可替换应用于配置根部的默认页边距。下面的示例在前缘的内容和背景之间创建了 10 个点的空间，在后缘创建了 20 个点的空间：

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.margins(.horizontal, 20.0)
```


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration/margins(_:_:)
crawled: 2025-12-03T07:00:27Z
---

# margins(_:_:)

**Instance Method**

Sets the margins around the content of the configuration.

## Declaration

```swift
func margins(_ edges: Edge.Set = .all, _ insets: EdgeInsets) -> UIHostingConfiguration<Content, Background>
```

## Parameters

- **edges**: The edges to apply the insets. Any edges not specified will use the system default values. The default value is [all](../Edge/Set/all.zh-Hans.md).
- **insets**: The insets to apply.

## Discussion

Use this modifier to replace the default margins applied to the root of the configuration. The following example creates 10 points of space between the content and the background on the leading edge and 20 points of space on the trailing edge:

```swift
UIHostingConfiguration {
    Text("My Contents")
}
.margins(.horizontal, 20.0)
```

