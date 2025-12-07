--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/init(mass:stiffness:damping:allowOverDamping:)

抓取时间：2025-12-01T11:03:56Z

---

# init(mass:stiffness:damping:allowOverDamping:)

**Initializer**

创建一个具有指定质量、刚度和阻尼的弹簧。

## 声明

```swift
init(mass: Double = 1.0, stiffness: Double, damping: Double, allowOverDamping: Bool = false)
```

## 参数

- **mass**：指定连接到弹簧末端的对象的属性。

- **stiffness**：对应的弹簧系数。

- **damping**：定义如何因摩擦力而阻尼弹簧的运动。

## 创建弹簧

- **init(duration:bounce:)**：创建具有指定持续时间和回弹力的弹簧。

- **init(response:dampingRatio:)**：创建具有指定响应和阻尼比的弹簧。

- **init(settlingDuration:dampingRatio:epsilon:)**：创建具有指定持续时间和阻尼比的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/init(mass:stiffness:damping:allowOverDamping:)
crawled: 2025-12-01T11:03:56Z
---

# init(mass:stiffness:damping:allowOverDamping:)

**Initializer**

Creates a spring with the specified mass, stiffness, and damping.

## Declaration

```swift
init(mass: Double = 1.0, stiffness: Double, damping: Double, allowOverDamping: Bool = false)
```

## Parameters

- **mass**: Specifies that property of the object attached to the end of the spring.
- **stiffness**: The corresponding spring coefficient.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.

## Creating a spring

- **init(duration:bounce:)**: Creates a spring with the specified duration and bounce.
- **init(response:dampingRatio:)**: Creates a spring with the specified response and damping ratio.
- **init(settlingDuration:dampingRatio:epsilon:)**: Creates a spring with the specified duration and damping ratio.

