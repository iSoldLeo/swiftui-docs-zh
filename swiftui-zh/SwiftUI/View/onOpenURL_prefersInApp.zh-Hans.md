--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onOpenURL(prefersInApp:)

抓取时间：2025-11-30T21:10:06Z

---

# onOpenURL(prefersInApp:)

**实例方法**

设置一个 `OpenURLAction`，该对象优先使用应用内浏览器打开 URL。它等效于调用 `.onOpenURL(_:)`

## 声明

```swift
@MainActor @preconcurrency func onOpenURL(prefersInApp: Bool) -> some View

```

## 讨论

```swift
.onOpenURL { _ in
    .systemAction(prefersInApp: prefersInApp)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/onOpenURL(prefersInApp:)
crawled: 2025-11-30T21:10:06Z
---

# onOpenURL(prefersInApp:)

**Instance Method**

Sets an `OpenURLAction` that prefers opening URL with an in-app browser. It’s equivalent to calling `.onOpenURL(_:)`

## Declaration

```swift
@MainActor @preconcurrency func onOpenURL(prefersInApp: Bool) -> some View

```

## Discussion

```swift
.onOpenURL { _ in
    .systemAction(prefersInApp: prefersInApp)
}
```

