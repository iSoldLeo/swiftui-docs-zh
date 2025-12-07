--- 来源：https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/actions-swift.property
抓取时间：2025-12-03T06:41:41Z

---

# 操作

**实例属性**

与节关联的自定义操作。

## 声明

```swift
var actions: SectionConfiguration.Actions { get }
```

## 说明

此属性提供对在 [Section](../Section.zh-Hans.md) 上定义的操作的编程访问。如果未指定任何操作，则集合为空。以下 `MailboxView` 会在操作过多而无法直接显示时，将其放入溢出菜单中。

```swift
struct MailboxView<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        ForEach(sections: content) { section in
            HStack {
                section.header
                Spacer()
                Group(subviews: section.actions) { actions in
                    if actions.count > 2 {
                        actions[0]
                        // Place the extras in an overflow menu.
                        Menu("Actions", systemImage: "plus") {
                            actions[1...]
                        }
                    } else {
                        actions
                    }
                }
            }
            section.content
        }
    }
}
```

然后，您可以在 `MailboxView` 中使用操作，而无需考虑溢出。

```swift
MailboxView {
    Section("iCloud") {
        Label("Receipts", systemImage: "folder")
        Label("Mailing Lists", systemImage: "folder")
    }
    .sectionActions {
        Button("New", systemImage: "folder.badge.plus") {}
        Button("Edit", systemImage: "folder.badge.gearshape") {}
        Button("Delete", systemImage: "folder.badge.minus") {}
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/actions-swift.property
crawled: 2025-12-03T06:41:41Z
---

# actions

**Instance Property**

Custom actions associated with a section.

## Declaration

```swift
var actions: SectionConfiguration.Actions { get }
```

## Discussion

This property provides programmatic access to the actions defined on a [Section](../Section.zh-Hans.md). If no actions were specified, the collection will be empty. The following `MailboxView` will put actions into an overflow menu if there are too many to display inline.

```swift
struct MailboxView<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        ForEach(sections: content) { section in
            HStack {
                section.header
                Spacer()
                Group(subviews: section.actions) { actions in
                    if actions.count > 2 {
                        actions[0]
                        // Place the extras in an overflow menu.
                        Menu("Actions", systemImage: "plus") {
                            actions[1...]
                        }
                    } else {
                        actions
                    }
                }
            }
            section.content
        }
    }
}
```

You can then use actions in `MailboxView` without considering overflow.

```swift
MailboxView {
    Section("iCloud") {
        Label("Receipts", systemImage: "folder")
        Label("Mailing Lists", systemImage: "folder")
    }
    .sectionActions {
        Button("New", systemImage: "folder.badge.plus") {}
        Button("Edit", systemImage: "folder.badge.gearshape") {}
        Button("Delete", systemImage: "folder.badge.minus") {}
    }
}
```

