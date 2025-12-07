--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchScopeActivation
抓取时间：2025-12-02T17:31:44Z

---

# 搜索范围激活

**Structure**

可搜索修饰符显示或隐藏搜索范围的方式。

## 声明

```swift
struct SearchScopeActivation
```

## 获取搜索范围激活类型

- **automatic**：自动激活搜索范围栏。

- **onSearchPresentation**：在显示搜索框后显示搜索范围，在取消搜索后隐藏搜索范围。

- **onTextEntry**：在搜索框中开始输入时显示搜索范围，在取消搜索后隐藏搜索范围。

## 限制搜索范围

- **限定搜索范围**：将搜索空间划分为几个大类。

- **searchScopes(_:scopes:)**：配置此视图的搜索范围。

- **searchScopes(_:activation:_:)**：使用指定的激活策略配置此视图的搜索范围。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchScopeActivation
crawled: 2025-12-02T17:31:44Z
---

# SearchScopeActivation

**Structure**

The ways that searchable modifiers can show or hide search scopes.

## Declaration

```swift
struct SearchScopeActivation
```

## Getting search scope activiation types

- **automatic**: The automatic activation of the scope bar.
- **onSearchPresentation**: An activation where the system shows search scopes after presenting search and hides search scopes after search cancellation.
- **onTextEntry**: An activation where the system shows search scopes when typing begins in the search field and hides search scopes after search cancellation.

## Limiting search scope

- **Scoping a search operation**: Divide the search space into a few broad categories.
- **searchScopes(_:scopes:)**: Configures the search scopes for this view.
- **searchScopes(_:activation:_:)**: Configures the search scopes for this view with the specified activation strategy.

