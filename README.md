# 编译选项

## 自动编译文件

编译文件时，使用 -w 指令后，TS 编译器会自动监视文件的变化，并在文件发生变化时对文件进行重新编译。

```sh
tsc xxx.js -w
```

## 自动编译整个项目

在项目根目录下创建一个 ts 的配置文件 tsconfig.json，tsconfig.json 是一个 JSON 文件，添加配置文件后，只需执行 tsc 命令即可完成对整个项目的编译
配置选项

### include

- 定义希望被编译文件所在的目录
- 默认值：["**/*"]

```json
"include":["src/**/*", "tests/**/*"]
```

### exclude

- 定义需要排除在外的目录
- 默认值：["node_modules", "bower_components", "jspm_packages"]

```json
"exclude": ["./src/hello/**/*"]
```

### compilerOptions

- 编译选项是配置文件中非常重要也比较复杂的配置选项
- 在 compilerOptions 中包含多个子选项，用来完成对编译的配置

1.  target

    - 设置 ts 代码编译的目标版本
    - 可选值 (ES3（默认）、ES5、ES6/ES2015、ES7/ES2016、ES2017、ES2018、ES2019、ES2020、ESNext)

2.  lib
    - 指定代码运行时所包含的库（宿主环境）
    - 可选值：ES5、ES6/ES2015、ES7/ES2016、ES2017、ES2018、ES2019、ES2020、ESNext、DOM、WebWorker、ScriptHost ......
3.  module
    - 设置编译后代码使用的模块化系统
    - 可选值：CommonJS、UMD、AMD、System、ES2020、ESNext、None
4.  outDir
    - 编译后文件的所在目录
    - 默认情况下，编译后的 js 文件会和 ts 文件位于相同的目录，设置 outDir 后可以改变编译后文件的位置
5.  outFile
    - 将所有的文件编译为一个 js 文件
    - 默认会将所有的编写在全局作用域中的代码合并为一个 js 文件，如果 module 制定了 None、System 或 AMD 则会将模块一起合并到文件之中
6.  rootDir
    - 指定代码的根目录，默认情况下编译后文件的目录结构会以最长的公共目录为根目录，通过 rootDir 可以手动指定根目录
7.  allowJs
    - 是否对 js 文件编译
8.  checkJs
    - 是否对 js 文件进行检查
9.  removeComments
    - 是否删除注释
    - 默认值：false
10. noEmit
    - 不对代码进行编译
    - 默认值：false
11. sourceMap
    - 是否生成 sourceMap
    - 默认值：false
