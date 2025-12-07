---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonRole/destructive
抓取时间： 2025-12-03T06:21:52Z
---

# 破坏性

**类型属性**

表示破坏性按钮的角色。

## 声明

```swift
static let destructive: ButtonRole
```

## 讨论

该角色用于删除用户数据或执行不可逆操作的按钮。破坏性按钮通过其外观提示用户应仔细考虑是否点击或单击该按钮。例如，SwiftUI 将使用[swipeActions(edge:allowsFullSwipe:content:)](../View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md)修饰符添加的破坏性按钮显示为红色背景：

```swift
List {
    ForEach(items) { item in
        Text(item.title)
            .swipeActions {
                Button(role: .destructive) { delete() } label: {
                    Label("Delete", systemImage: "trash")
                }
            }
    }
}
.navigationTitle("Shopping List")
```



## 获取按钮作用

- **cancel**：表示取消操作的按钮的角色。


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonRole/destructive
crawled: 2025-12-03T06:21:52Z
---

# destructive

**Type Property**

A role that indicates a destructive button.

## Declaration

```swift
static let destructive: ButtonRole
```

## Discussion

Use this role for a button that deletes user data, or performs an irreversible operation. A destructive button signals by its appearance that the user should carefully consider whether to tap or click the button. For example, SwiftUI presents a destructive button that you add with the [swipeActions(edge:allowsFullSwipe:content:)](../View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md) modifier using a red background:

```swift
List {
    ForEach(items) { item in
        Text(item.title)
            .swipeActions {
                Button(role: .destructive) { delete() } label: {
                    Label("Delete", systemImage: "trash")
                }
            }
    }
}
.navigationTitle("Shopping List")
```



## Getting button roles

- **cancel**: A role that indicates a button that cancels an operation.

