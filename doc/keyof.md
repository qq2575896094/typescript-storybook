# keyof类型运算符

> 该`keyof`运算符作用于对象类型并生成其键的字符串或数字文字联合.类似于 `type P = 'x' | 'y'`

```typescript
type Point = { x: number, y: number }
type P = keyof Point
```

> 如果类型具有`string`或`number`索引签名, `keyof`则将返回这些类型
> Mis string | number— 这是因为 JavaScript 对象键始终被强制转换为字符串，因此obj[0]始终与 相同obj["0"]。
````typescript
type Arrayish = { [n: number]: unknown }

// type A = number
type A = keyof Arrayish

type Mapish = { [k: string]: boolean }
// type M = string | number
type M = keyof Mapish


const a: M = 12
const bb: M = '12'
````
