# Contributing to Tokei

* [Language Addition](#language-addition)
* [Bug Reports](#bug-reports)

# Language Addition
Currently tokei generates languages from the [`languages.json`](languages.json)
file. JSON was decided to make it easy to add new languages, and change code
structure without changing large data structures. Here we will go over the
properties of a language in `languages.json`, through examples.

```
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
```

Above is the JavaScript's definition. The first thing that needs to be defined
is the key, the keys format should be same as 
[Rust's enum style].
As this key will be used in an enum for identifying the language. For a lot of 
language's this also works for showing the language when we print to the screen. 
However there are some languages whose names don't work with the enum style.
For example `JSON` is usually shown in all caps, but that doesn't fit in Rust's
enum style. So we have an additional optional field called `name`, which defines
how the language should look when displayed to the user.

```json
"Json" {
    "name": "JSON",
```

For defining comments has a few properties: firstly is the most commonly used
`single` property which defines single line comments. Comments which don't
continue onto the next line.

```rust
let x = 5; // default x position
let y = 0; // default y position
```

The `single` property expects an array of strings, as some languages have 
multiple syntaxes for defining a a single line comment. For example `PHP` allows
both `#` and `//` as comments.

```json
"Php": {
    "single": [
        "#",
        "//"
    ]
```

For defining comments that also have a ending syntax, there is the `multi_line`
property.

```rust
let x = /* There is a reason
    for this comment I swear */
    10;
```

A lot of languages have the same commenting syntax usually inheriting from the 
authors previous language or preferred language. In order to avoid code reuse
tokei's languages have a `base` property which says to use a common comment
syntax. e.g.

```json
"ActionScript":{
    "base":"c",
    "extensions":[
        "as"
    ]
}
```

#### Bases

- `blank` A language with no comments.
- `c` Single: `//`, Multi line: `/* */`, Quotes: `" "`
- `func` Multi line: `(* *)`, Quotes: `" "`
- `html` Multi line: `<!-- -->`, Quotes: `" "`
- `hash` Single: `#`
- `haskell` Single: `--`, Multi line: `{- -}`, Nested: `true`
- `pro` Single: `%`, Multi line: `/* */`, Quotes: `" "`


Some languages have a single, standard filename with no extension
like `Makefile` or `Dockerfile`. These can be defined with the
`filenames` property:

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

Filenames should be all-lowercase, whether or not the filename
typically has capital letters included.

Note that filenames will **override** extensions with the
following definition a file named `CMakeLists.txt` will be
detected as a `CMake` file, not a `Text` file.

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

# Tests
A test file is required with language additions. The file should
contain every variant comments and quotes, as well as a comment
at the top of the file containing the manually verified lines,
code, comments, blanks e.g.
`// 39 lines 32 code 2 comments 5 blanks`. The comment should use
the syntax of the language you're testing. A good example of a
test file is [`tests/data/rust.rs`].

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

# Bug Reports
Please include the error message, and a minimum working example
including the file, or file structure.

```
This file crashes the program.

<filename>
\`\`\`
\`\`\`
```

[Rust's enum style]: (https://github.com/rust-lang/rfcs/blob/master/text/0430-finalizing-naming-conventions.md#general-naming-conventions)
[`tests/data/rust.rs`]: https://github.com/Aaronepower/tokei/blob/master/tests/data/rust.rs
