---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonRole/confirm
抓取时间： 2025-12-03T06:21:53Z
---

# 确认

**类型属性**

表示确认操作的按钮。

## 声明

```swift
static let confirm: ButtonRole
```

## 讨论

以下视图将在工具栏中显示一个确认按钮。

```swift
struct NewContactSheet: View {
    var body: some View {
        NavigationStack {
            NewContactEditor()
                .toolbar {
                    Button(role: .confirm) {
                        saveChanges()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonRole/confirm
crawled: 2025-12-03T06:21:53Z
---

# confirm

**Type Property**

A role that indicates a button that confirms an operation.

## Declaration

```swift
static let confirm: ButtonRole
```

## Discussion

The following view would display a confirm button in the toolbar.

```swift
struct NewContactSheet: View {
    var body: some View {
        NavigationStack {
            NewContactEditor()
                .toolbar {
                    Button(role: .confirm) {
                        saveChanges()
                    }
                }
        }
    }
}
```

