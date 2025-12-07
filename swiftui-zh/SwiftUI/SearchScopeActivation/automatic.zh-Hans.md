--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchScopeActivation/automatic

抓取时间：2025-12-03T06:05:31Z

---

# automatic

**Type 属性**

自动激活搜索范围栏。

## 声明

```swift
static var automatic: SearchScopeActivation { get }
```

## 讨论

默认情况下，iOS 中为 [onTextEntry](onTextEntry.zh-Hans.md)，macOS 中为 [onSearchPresentation](onSearchPresentation.zh-Hans.md)。

## 获取搜索范围激活类型

- **onSearchPresentation**：激活后，系统在显示搜索框后显示搜索范围，并在取消搜索后隐藏搜索范围。

- **onTextEntry**：激活后，系统在搜索框中开始输入时显示搜索范围，并在取消搜索后隐藏搜索范围。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchScopeActivation/automatic
crawled: 2025-12-03T06:05:31Z
---

# automatic

**Type Property**

The automatic activation of the scope bar.

## Declaration

```swift
static var automatic: SearchScopeActivation { get }
```

## Discussion

By default, this is [onTextEntry](onTextEntry.zh-Hans.md) in iOS and [onSearchPresentation](onSearchPresentation.zh-Hans.md) in macOS.

## Getting search scope activiation types

- **onSearchPresentation**: An activation where the system shows search scopes after presenting search and hides search scopes after search cancellation.
- **onTextEntry**: An activation where the system shows search scopes when typing begins in the search field and hides search scopes after search cancellation.

