# `canActivate(transition) [-> Promise | Boolean]`

在验证阶段，当一个组件将要被切入的时候被调用。

### 参数

- [`transition {Transition}`](hooks.md#transition-object)

  调用 `transition.next()` 可以断定（ resolve ）此勾子函数。调用 `transition.abort()` 可以无效化并取消此次切换。

### 返回值

- 可选择性返回 Promise :

  - `resolve(true)` -> `transition.next()`
  - `resolve(false)` -> `transition.abort()`
  - `reject(reason)` -> `transition.abort(reason)`

- 可选择性返回 Boolean 值：

  - `true` -> `transition.next()`
  - `false` -> `transition.abort()`

### 详情

此勾子函数的调用顺序是从上之下。子级组件视图的 `canActivate` 勾子仅在父级组件的 `canActivate` 被断定（ resolved ）之后调用。
