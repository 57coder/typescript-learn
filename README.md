# TypeScript 中的基本类型

- 类型

| 类型    | 例子              | 描述                            |
| ------- | ----------------- | ------------------------------- |
| number  | 1, -33, 2.5       | 任意数字                        |
| ------- | ----------------- | ------------------------------  |
| string  | 'hi', "hi", hi    | 任意字符串                      |
| boolean | true、false       | 布尔值 true 或 false            |
| 字面量  | 其本身            | 限制变量的值就是该字面量的值    |
| any     | \*                | 任意类型                        |
| unknown | \*                | 未知类型                        |
| void    | 空值（undefined） | 没有值（或 undefined）          |
| never   | 没有值            | 不能是任何值                    |
| object  | {name:'孙悟空'}   | 任意的 JS 对象                  |
| array   | [1,2,3]           | 任意 JS 数组                    |
| tuple   | [4,5]             | 元组，TS 新增类型，固定长度数组 |
| enum    | enum{A, B}        | 枚举，TS 中新增类型             |

- number

```js
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
let big: bigint = 100n;
```

- boolean

```js
let isDone: boolean = false;
```

- string

```js
let color: string = "blue";
color = "red";

let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}.

I'll be ${age + 1} years old next month.`;
```

- 字面量

```js
// 可以使用字面量去指定变量的类型，通过字面量可以确定变量的取值范围
let color: "red" | "blue" | "black";
color = "red";
let num: 1 | 2 | 3 | 4 | 5;
```

- any (不建议使用)

```js
let d: any = 4;
d = "hello";
d = true;
```

- unknown

```js
// unknown类型的变量不可以直接赋值给其他变量
let notSure: unknown = 4;
notSure = "hello";
```

- void

```js
let unusable: void = undefined;
```

- never

```js
function error(message: string): never {
  throw new Error(message);
}
```

- object (没啥用)

```js
let obj: object = {};
```

- array

```js
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
```

- tuple

```js
let x: [string, number];
x = ["hello", 10];
```

- enum

```js
enum Color {
  Red,
  Green,
  Blue,
}
let c: Color = Color.Green;

enum Color {
  Red = 1,
  Green,
  Blue,
}
let c: Color = Color.Green;

enum Color {
  Red = 1,
  Green = 2,
  Blue = 4,
}
let c: Color = Color.Green;
```
