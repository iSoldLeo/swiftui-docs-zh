---
来源：https://developer.apple.com/documentation/SwiftUI/Group/init(章节：转换:)
抓取时间：2025-12-02T20:59:20Z
---

# init(sections:transform:)

**Initializer**

用给定视图的截面构建一个分组。

## 声明

```swift
init<Base, Result>(sections view: Base, @ViewBuilder transform: @escaping (SectionCollection) -> Result) where Content == GroupSectionsOfContent<Base, Result>, Base : View, Result : View
```

## 参数

- **view**：要提取部分的视图。

## 讨论

各部分都是按需构建的，因此只需访问该集合中创建结果内容所需的部分即可。

```swift
struct SectionedStack<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        VStack {
            Group(sections: content) { sections in
                ForEach(sections) { section in
                    SectionChrome {
                        section.content
                    } header: {
                        section.header
                    } footer: {
                        section.footer
                    }
                }
            }
        }
    }
}
```

通过使用基于视图构建器的初始化程序创建`SectionedStack`，就可以使用该程序。

```swift
SectionedStack {
    Section("Header A") {
        Text("Hello")
        Text("World")
    } footer: {
        Text("Footer A")
    }
    Section("Header B") {
        Text("Foo")
        Text("Bar")
    } footer: {
        Text("Footer B")
    }
}
```

给定视图中未明确指定为部分的任何内容都会与其同级内容组合成隐式部分，这意味着`SectionCollection` 中的部分最少为一个。例如，在下面的`SectionedStack` 中，有一个显式部分，以及两个隐式部分，分别包含显式部分之前和之后的内容：

```swift
SectionedStack {
    Text("First implicit section")
    Section("Explicit section") {
        Text("Content")
    }
    Text("Second implicit section")
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Group/init(sections:transform:)
crawled: 2025-12-02T20:59:20Z
---

# init(sections:transform:)

**Initializer**

Constructs a group from the sections of the given view.

## Declaration

```swift
init<Base, Result>(sections view: Base, @ViewBuilder transform: @escaping (SectionCollection) -> Result) where Content == GroupSectionsOfContent<Base, Result>, Base : View, Result : View
```

## Parameters

- **view**: The view to extract the sections of.

## Discussion

Sections are constructed lazily, on demand, so access only as much of this collection as is necessary to create the resulting content.

```swift
struct SectionedStack<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        VStack {
            Group(sections: content) { sections in
                ForEach(sections) { section in
                    SectionChrome {
                        section.content
                    } header: {
                        section.header
                    } footer: {
                        section.footer
                    }
                }
            }
        }
    }
}
```

This can then be used by creating a `SectionedStack` with it’s view builder-based initializer.

```swift
SectionedStack {
    Section("Header A") {
        Text("Hello")
        Text("World")
    } footer: {
        Text("Footer A")
    }
    Section("Header B") {
        Text("Foo")
        Text("Bar")
    } footer: {
        Text("Footer B")
    }
}
```

Any content of the given view which is not explicitly specified as a section is grouped with its sibling content to form implicit sections, meaning the minimum number of sections in a `SectionCollection` is one. For example in the following `SectionedStack`, there is one explicit section, and two implicit sections containing the content before, and after the explicit section:

```swift
SectionedStack {
    Text("First implicit section")
    Section("Explicit section") {
        Text("Content")
    }
    Text("Second implicit section")
}
```

