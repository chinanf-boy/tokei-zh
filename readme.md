# tokei [![translate-svg]][translate-list] 

[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list

「 Tokei是一个显示代码信息的统计程序 」

[中文](./readme.md) | [english](https://github.com/Aaronepower/tokei)


---

## 校对 ✅

<!-- doc-templite START generated -->
<!-- repo = 'Aaronepower/tokei' -->
<!-- commit = 'a9a185e6e9c7d6c472736aadaf8ecc69d202b3c9' -->
<!-- time = '2018 8.29' -->
翻译的原文 | 与日期 | 最新更新 | 更多
---|---|---|---
[commit] | ⏰ 2018 8.29 | ![last] | [中文翻译][translate-list]

[last]: https://img.shields.io/github/last-commit/Aaronepower/tokei.svg
[commit]: https://github.com/Aaronepower/tokei/tree/a9a185e6e9c7d6c472736aadaf8ecc69d202b3c9

<!-- doc-templite END generated -->

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---


# Tokei ([时计](https://en.wiktionary.org/wiki/%E6%99%82%E8%A8%88)) 

[![Linux build status](https://img.shields.io/travis/Aaronepower/tokei.svg?branch=master)](https://travis-ci.org/Aaronepower/tokei)
[![Windows build status](https://ci.appveyor.com/api/projects/status/github/Aaronepower/tokei?svg=true)](https://ci.appveyor.com/project/Aaronepower/tokei)
[![](https://img.shields.io/crates/d/tokei.svg)](https://crates.io/crates/tokei)
[![](https://img.shields.io/github/issues-raw/Aaronepower/tokei.svg)](https://github.com/Aaronepower/tokei/issues)
[![](https://tokei.rs/b1/github/Aaronepower/tokei?category=code)](https://github.com/Aaronepower/tokei)
[![Documentation](https://docs.rs/tokei/badge.svg)](https://docs.rs/tokei/)
[![Donate using Liberapay](https://liberapay.com/assets/widgets/donate.svg)](https://liberapay.com/Aaronepower/donate)

Tokei是一个显示代码信息的统计程序. Tokei将显示文件数,和这些文件中的总行数以及按语言分组的代码,注释和空格. 

## 示例输出

这是tokei在自己的目录上运行

[![asciicast](https://asciinema.org/a/d14m9g1d2cyo7wvrxh0z4ck6o.png)](https://asciinema.org/a/d14m9g1d2cyo7wvrxh0z4ck6o?autoplay=1)

## [文档](https://docs.rs/tokei)

## 目录

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [特征](#%E7%89%B9%E5%BE%81)
- [安装](#%E5%AE%89%E8%A3%85)
  - [自动](#%E8%87%AA%E5%8A%A8)
    - [Arch Linux](#arch-linux)
    - [Cargo](#cargo)
    - [Conda](#conda)
    - [Fedora](#fedora)
    - [FreeBSD](#freebsd)
    - [brew](#brew)
    - [Nix/NixOS](#nixnixos)
  - [手册](#%E6%89%8B%E5%86%8C)
      - [Linux](#linux)
      - [OSX](#osx)
      - [windows](#windows)
- [如何使用Tokei](#%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8tokei)
    - [基本用法](#%E5%9F%BA%E6%9C%AC%E7%94%A8%E6%B3%95)
    - [多个文件夹](#%E5%A4%9A%E4%B8%AA%E6%96%87%E4%BB%B6%E5%A4%B9)
    - [排除文件夹](#%E6%8E%92%E9%99%A4%E6%96%87%E4%BB%B6%E5%A4%B9)
    - [排序输出](#%E6%8E%92%E5%BA%8F%E8%BE%93%E5%87%BA)
    - [输出文件统计信息](#%E8%BE%93%E5%87%BA%E6%96%87%E4%BB%B6%E7%BB%9F%E8%AE%A1%E4%BF%A1%E6%81%AF)
    - [输出为不同的格式](#%E8%BE%93%E5%87%BA%E4%B8%BA%E4%B8%8D%E5%90%8C%E7%9A%84%E6%A0%BC%E5%BC%8F)
    - [读取存储格式](#%E8%AF%BB%E5%8F%96%E5%AD%98%E5%82%A8%E6%A0%BC%E5%BC%8F)
- [选项](#%E9%80%89%E9%A1%B9)
- [徽章](#%E5%BE%BD%E7%AB%A0)
- [插件](#%E6%8F%92%E4%BB%B6)
- [支持的语言](#%E6%94%AF%E6%8C%81%E7%9A%84%E8%AF%AD%E8%A8%80)
- [常见问题](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  - [Tokei说我有很多D代码,但我知道没有D代码!](#tokei%E8%AF%B4%E6%88%91%E6%9C%89%E5%BE%88%E5%A4%9Ad%E4%BB%A3%E7%A0%81%E4%BD%86%E6%88%91%E7%9F%A5%E9%81%93%E6%B2%A1%E6%9C%89d%E4%BB%A3%E7%A0%81)
- [规范来源](#%E8%A7%84%E8%8C%83%E6%9D%A5%E6%BA%90)
- [版权和许可](#%E7%89%88%E6%9D%83%E5%92%8C%E8%AE%B8%E5%8F%AF)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 特征

-   Tokei是**非常快的**,看看我们的[对照](./COMPARISON.zh.md)文件,了解Tokei的速度与其他人的比较. 

-   Tokei是**准确**,Tokei正确处理多行注释,嵌套注释,而不计算字符串中的注释. 提供准确的代码统计信息. 

-   Tokei拥有广泛的语言,支持**150**语言及其各种扩展. 

-   Tokei可以输出多种格式 (**CBOR**,**JSON**,**TOML**,**YAML**) ,容易存储和重复使用. 这些也可以在tokei中重复使用,将先前运行的统计数据与另一组进行组合. 

-   Tokei可用**苹果电脑**,**Linux**,和**Windows**. 看到[安装说明](#安装)如何在您的平台上获得Tokei. 

-   Tokei也是一个**rust-箱**允许您轻松地将其与其他项目集成. 

## 安装

### 自动

#### Arch Linux

```shell
$ pacman -S tokei
```

#### Cargo

```shell
$ cargo install tokei
```

#### Conda

```shell
$ conda install -c conda-forge tokei
```

#### Fedora

```shell
$ sudo dnf install tokei
```

#### FreeBSD

```shell
$ pkg install tokei
```

#### brew

```shell
$ brew install tokei
```

#### Nix/NixOS

```shell
$ nix-env -i tokei
```

### 手册

您可以在[发布页面](https://github.com/Aaronepower/tokei/releases)中下载预建的二进制文件,或从源创建. 

```shell
$ git clone https://github.com/Aaronepower/tokei.git
$ cd tokei
$ cargo build --release
```

##### Linux

    # sudo mv target/release/tokei /usr/local/bin

##### OSX

    # sudo mv target/release/tokei /usr/local/bin/tokei

##### windows

-   为tokei创建一个文件夹
-   搜索`env`
-   打开"编辑你的环境变量"
-   编辑`PATH`
-   将文件夹路径追加到字符串末尾即: `<path_stuff_here>;C:/tokei/;`

## 如何使用Tokei

#### 基本用法

这是使用tokei的基本方法. 这会报告`./foo`和所有子文件夹代码. 

```shell
$ tokei ./foo
```

#### 多个文件夹

要在同一个调用中对多个文件夹进行tokei报告,只需添加一个`逗号`或`一个空格`,后跟另一个路径. 

```shell
$ tokei ./foo ./bar ./baz
```

```shell
$ tokei ./foo, ./bar, ./baz
```

#### 排除文件夹

Tokei会忽略`.gitignore`和`.ignore`文件中的匹配,你也可以使用`--exclude`忽略文件的选项. 该`--exclude`具有与`.gitignore`相同的语义. 

```shell
$ tokei ./foo --exclude *.rs
```

#### 排序输出

默认情况下,tokei按语言名称按字母顺序排序,但使用`--sort`也可以按任何列排序. 

`blanks, code, comments, lines`

```shell
$ tokei ./foo --sort code
```

#### 输出文件统计信息

默认情况下,tokei仅输出语言的总和,如使用`--files`,还可以输出单个文件统计信息. 

```shell
$ tokei ./foo --files
```

#### 输出为不同的格式

Tokei通常输出为为终端设计的漂亮的人类可读格式. 还有使用`--output`选项各种其他格式,对于将数据带入另一个程序更有用. 

**注意:** 这个版本的tokei编译时,没有任何序列化格式,以启用序列化,使用features标志重新安装tokei. 

```shell
  ALL:
  cargo install tokei --features all

  JSON:
  cargo install tokei --features json

  CBOR:
  cargo install tokei --features cbor

  YAML:
  cargo install tokei --features yaml

  CBOR:
  cargo install tokei --features cbor
```

**目前支持的格式**

-   JSON`--output json`
-   YAML`--output yaml`
-   TOML`--output toml`
-   CBOR`--output cbor`

```shell
$ tokei ./foo --output json
```

#### 读取存储格式

Tokei还可以将之前结果中添加的输出格式输入到当前运行中. Tokei可以获取文件的路径,传入的格式作为选项的值,或者 从stdin获取. 

```shell
$ tokei ./foo --input ./stats.json
```

## 选项

    tokei 7.0.1
    Aaron P. <theaaronepower@gmail.com> + Contributors
    A utility that allows you to count code, quickly.

    USAGE:
        tokei [FLAGS] [OPTIONS] [--] [input]...

    FLAGS:
        -f, --files        Will print out statistics on individual files.
        -h, --help         Prints help information
        -l, --languages    Prints out supported languages and their extensions.
        -V, --version      Prints version information
        -v, --verbose      Set log output level:
                                    1: to show unknown file extensions,
                                    2: reserved for future debugging,
                                    3: enable file level trace. Not recommended on multiple files

    OPTIONS:
        -e, --exclude <exclude>...    忽略包含该单词的所有文件和目录。
        -i, --input <file_input>      提供之前的tokei运行的统计数据。 可以给出文件路径，或 'stdin'
                                      从stdin读取。
        -o, --output <output>         以特定格式输出Tokei。 [值：cbor，json，toml，yaml]
        -s, --sort <sort>             根据列[值: files, lines, blanks, code, comments]对语言进行排序

    ARGS:
        <input>...    The input file(s)/directory(ies) to be counted.

## 徽章

Tokei支持徽章. 例如[![](https://tokei.rs/b1/github/Aaronepower/tokei)](https://github.com/Aaronepower/tokei). 

    [![](https://tokei.rs/b1/github/Aaronepower/tokei)](https://github.com/Aaronepower/tokei).

Tokei的URL方案如下. 

    https://tokei.rs/{host: values: github|gitlab}/{Repo Owner eg: Aaronepower}/{Repo name eg: tokei}

默认情况下,徽章将显示项目的LoC (*代码行*) ,你也可以通过使用指定它来显示不同的类别`?category=`请求参数. 它可以是`code`,`blanks`,`files`,`lines`,`comments`,示例显示总行数: 

    [![](https://tokei.rs/b1/github/Aaronepower/tokei?category=lines)](https://github.com/Aaronepower/tokei).

## 插件

感谢贡献者tokei,现在可以作为一些文本编辑器的插件. 

-   [Vim](https://github.com/vmchale/tokei-vim)通过[vmchale](https://github.com/vmchale/)

## 支持的语言

如果您要添加某种语言,请随时提交包含以下信息的提取请求. 如果你不确定,看看[`languages.json`](./languages.json)如何定义其他语言. 

-   语言名称
-   文件扩展名
-   评论语法 (*它有区块评论吗?它和C一样吗?*) 
-   字符串文字语法

```
ABAP
ActionScript
Ada
Alex
Agda
ASP
ASP.NET
Assembly
Autoconf
SH
AutoHotKey
BASH
FISH
Batch
C
C Header
C#
C Shell
Cabal
Cassius
Ceylon
Clojure
CMake
COBOL
CoffeeScript
Cogent
ColdFusion
ColdFusion CFScript
Coq
C++
C++ Header
CSS
Crystal
D
Dart
Device Tree
Dockerfile
Elixir
Elm
Emacs Development Environment
Emacs Lisp
Erlang
FEN
Forth
F*
F#
FORTRAN Legacy
FORTRAN Modern
GDScript
GLSL
Go
Groovy
Happy
Handlebars
Haskell
Haxe
HCL
HEX
HTML
Hamlet
Idris
Intel HEX
Isabelle
JAI
Java
JavaScript
JSON
JSX
Julia
Julius
Kotlin
Lean
LESS
LD Script
LISP
Lua
Lucius
Madlang
Makefile
Markdown
Meson
Mint
ModuleDef
Mustache
Nim
Nix
OCaml
Objective C
Objective C++
Org mode
Oz
Pascal
Perl
PHP
Polly
Processing
Prolog
Protocol Buffers
PSL Assertions
PureScript
Python
QCL
QML
R
Racket
Rakefile
Razor
ReStructuredText
Ruby
Ruby HTML
Rust
Sass
Scala
Scons
SRecode Template
Standard ML
Specman e
SPICE Netlists
SQL
SVG
Swift
SystemVerilog
TCL
TeX
Plain Text
TOML
TypeScript
Unreal Script
Ur/Web
Vala
VB6
VBScript
Verilog
Verilog argument files
VHDL
Vim Script
Wolfram
Xaml
XML
Xtend
YAML
Zsh
```

## 常见问题

### Tokei说我有很多D代码,但我知道没有D代码!

这可能是由于`gcc`生成`.d`文件. 在D用户决定使用其他文件扩展名之前,您始终可以排除`.d`的文件,使用`-e --exclude`这样的选项

    $ tokei . -e *.d

## 规范来源

这个仓库的规范来源是托管的[GitHub上](https://github.com/Aaronepower/tokei). 如果您有GitHub帐户,请提出您的问题,并在那里提出请求. 

## 版权和许可

 (C) Aaron Power和贡献者的2015版权所有

请参阅 [CONTRIBUTORS.md](./CONTRIBUTORS.zh.md) 以获取完整的贡献者列表. 

Tokei遵循 MIT许可和Apache许可 (版本2.0) 的条款. 

看到[许可证APACHE](./LICENCE-APACHE),[LICENSE-MIT](./LICENCE-MIT)了解更多信息. 
