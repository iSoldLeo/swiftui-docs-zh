--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyPress/Phases
抓取时间：2025-12-04T13:38:02Z

---

# KeyPress.Phases

**Structure**

用于匹配按键事件不同阶段的选项。

## 声明

```swift
struct Phases
```

## 获取按键阶段

- **down**：用户按下某个键。

- **up**：用户松开某个键。

- **repeat**：用户按住某个键以触发一系列重复事件。

- **all**：匹配所有按键阶段的值。

## 获取按键事件的阶段

- **phase**：按键事件的阶段（`.down`、`.repeat` 或 `.up`）。

## 符合以下协议：

- CustomDebugStringConvertible

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/KeyPress/Phases
crawled: 2025-12-04T13:38:02Z
---

# KeyPress.Phases

**Structure**

Options for matching different phases of a key-press event.

## Declaration

```swift
struct Phases
```

## Getting the phases

- **down**: The user pressed down on a key.
- **up**: The user released a key.
- **repeat**: The user held a key down to issue a sequence of repeating events.
- **all**: A value that matches all key press phases.

## Getting the phase of the keypress

- **phase**: The phase of the key-press event (`.down`, `.repeat`, or `.up`).

## Conforms To

- CustomDebugStringConvertible
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

