
# 为Tokei做贡献

-   [语言增加](#language-addition)
-   [错误报告](#bug-reports)

# 语言增加

目前tokei从[`languages.json`](languages.json)文件中生成语言. JSON使,添加新语言变得容易,并且在不改变大数据结构的情况下改变代码结构. 在这里,我们将介绍一种语言的属性`languages.json`通过例子. 

    "JavaScript":{
        "base":"c",
        "quotes":[
            [
                "\\\"",
                "\\\""
            ],
            [
                "'",
                "'"
            ],
            [
                "`",
                "`"
            ]
        ],
        "extensions":[
            "js"
        ]
    },

以上是JavaScript的定义. 需要定义的第一件事是密钥,密钥格式应该是相同的[rust's enum style]]. 因为此密钥将在枚举中用于识别语言. 对于很多语言来说,这也适用于在我们打印到屏幕时显示语言. 但是,有些语言的名称不适用于枚举样式. 例如`JSON`通常以全部大写字母显示,但这不符合Rust的枚举风格. 所以我们有一个名为`name`的附加可选字段,它定义了语言在向用户显示时的外观. 

```json
"Json" {
    "name": "JSON",
```

对于定义注释有一些属性: 首先是最常用的`single`定义单行注释的属性. 注释不会继续下一行. 

```rust
let x = 5; // default x position
let y = 0; // default y position
```

该`single`属性需要一个字符串数组,因为某些语言有多种语法来定义单行注释. 例如`PHP`允许两者`#`和`//`作为注释. 

```json
"Php": {
    "single": [
        "#",
        "//"
    ]
```

为了定义也有结尾语法的注释,有`multi_line`属性. 

```rust
let x = /* There is a reason
    for this comment I swear */
    10;
```

许多语言具有相同的注释语法,通常继承自作者以前的语言或首选语言. 为了避免代码重用,tokei的语言有了`base`表示使用通用注释语法的属性. 例如

```json
"ActionScript":{
    "base":"c",
    "extensions":[
        "as"
    ]
}
```

#### bases

-   `blank`一种没有注释的语言. 
-   `c`单: `//`,多行: `/* */`,行情: `" "`
-   `func`多行: `(* *)`,行情: `" "`
-   `html`多行: `<!-- -->`,行情: `" "`
-   `hash`单: `#`
-   `haskell`单: `--`,多行: `{- -}`,嵌套: `true`
-   `pro`单: `%`,多行: `/* */`,行情: `" "`

有些语言有一个标准的文件名,没有扩展名,像`Makefile`要么`Dockerfile`. 这些可以用`filenames`属性: 

```json
"Makefile":{
    "filenames":[
        "makefile"
    ],
    "extensions":[
        "makefile",
        "mak",
        "mk"
    ]
}
```

无论文件名是否包含大写字母,文件名都应为全小写. 

请注意,文件名将会被定义的扩展名为`CMakeLists.txt`**覆盖**,将被检测为`CMake`文件,而不是`Text`文件. 

```json
"Text":{
    "extensions":[
        "txt"
    ]
},
"CMake":{
    "filenames": [
        "cmakelists.txt"
    ]
}
```

# 测试

添加语言时需要测试文件. 该文件应包含每个变体注释和引号,以及文件顶部的注释,其中包含手动验证的行,代码,注释,空格,例如`// 39 lines 32 code 2 comments 5 blanks`. 注释应该使用您正在测试的语言的语法. 测试文件的一个很好的例子是[`tests/data/rust.rs`]. 

```rust
// 39 lines 32 code 2 comments 5 blanks

/* /**/ */
fn main() {
    let start = "/*";
    loop {
        if x.len() >= 2 && x[0] == '*' && x[1] == '/' { // found the */
            break;
        }
    }
}

fn foo() {
    let this_ends = "a \"test/*.";
    call1();
    call2();
    let this_does_not = /* a /* nested */ comment " */
        "*/another /*test
            call3();
            */";
}

fn foobar() {
    let does_not_start = // "
        "until here,
        test/*
        test"; // a quote: "
    let also_doesnt_start = /* " */
        "until here,
        test,*/
        test"; // another quote: "
}

fn foo() {
    let a = 4; // /*
    let b = 5;
    let c = 6; // */
}
```

# 错误报告

请包含错误消息,以及包含文件或文件结构的最低工作示例. 

    This file crashes the program.

    <filename>
    \`\`\`
    \`\`\`

[rust's enum style]: (https://github.com/rust-lang/rfcs/blob/master/text/0430-finalizing-naming-conventions.md#general-naming-conventions)

[`tests/data/rust.rs`]: https://github.com/Aaronepower/tokei/blob/master/tests/data/rust.rs
