---
来源： https://developer.apple.com/documentation/swiftui/dropoperation/set
抓取时间： 2025-12-05T22:29:38Z
---

# DropOperation.Set

**Structure**

一组停顿操作，与`DropOperation`中的匹配情况相对应。

### 声明

```swift
struct Set
```

## Initializers

- **init(rawValue:)**：使用提供的原始值创建一组下拉操作。

## 类型属性

- **alias**：使用提供的原始值创建一组下拉操作。
- **cancel**：取消操作。
- **copy**：将数据复制到修改后的视图。
- **delete**：删除数据。
- **forbidden**：禁止操作。
- **move**： 删除数据：移动拖动项所代表的数据，而不是复制数据。

## 符合

- 可复制
- 自定义字符串可转换
- 可等价
- 可表达数组字素
- 可散列
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/swiftui/dropoperation/set
crawled: 2025-12-05T22:29:38Z
---

# DropOperation.Set

**Structure**

A set of drop operations, corresponding to matching cases in `DropOperation`.

## Declaration

```swift
struct Set
```

## Initializers

- **init(rawValue:)**: Creates a set of drop operations using the provided raw value.

## Type Properties

- **alias**
- **cancel**: Cancel the operation.
- **copy**: Copy the data to the modified view.
- **delete**: Delete the data.
- **forbidden**: The operation is forbidden.
- **move**: Move the data represented by the drag items instead of copying it.

## Conforms To

- Copyable
- CustomStringConvertible
- Equatable
- ExpressibleByArrayLiteral
- Hashable
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

