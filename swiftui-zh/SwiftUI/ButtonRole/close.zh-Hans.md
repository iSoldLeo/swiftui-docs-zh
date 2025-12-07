---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonRole/close
抓取时间： 2025-12-03T06:21:52Z
---

# 关闭

**类型属性**

表示关闭当前操作的按钮。

## 声明

```swift
static let close: ButtonRole
```

## 讨论

与取消操作不同，关闭操作不会丢失用户的进度。

以下视图将在工具栏中显示关闭按钮。

```swift
struct NewContactSheet: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        NavigationStack {
            NewContactEditor()
                .toolbar {
                    Button(role: .close) {
                        dismiss()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonRole/close
crawled: 2025-12-03T06:21:52Z
---

# close

**Type Property**

A role that indicates a button that closes the current operation.

## Declaration

```swift
static let close: ButtonRole
```

## Discussion

Unlike a cancel operation, a close operation doesn’t lose progress for a user.

The following view would display a close button in the toolbar.

```swift
struct NewContactSheet: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        NavigationStack {
            NewContactEditor()
                .toolbar {
                    Button(role: .close) {
                        dismiss()
                    }
                }
        }
    }
}
```

