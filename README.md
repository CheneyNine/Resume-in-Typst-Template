# CQU Resume Template in Typst

使用 Typst 编写的简历模板.

代码上，以[OrangeX4](https://github.com/OrangeX4/Chinese-Resume-in-Typst) 所提供的模板为基础，增加了一定的行距控制，丰富了图标内容。同时也参考了一部分Typst的[中文手册](https://typst-doc-cn.github.io/docs/tutorial/).

功能与外观上，参考了[doubleZ](https://github.com/doubleZ0108)的个人简历作品，非常感谢大佬的耐心指导.


## 使用


### 本地编辑（推荐）

- 安装 VS Code，以及 Typst LSP 和 vscode-pdf 插件。
- 打开 `resume_gne.typ` 文件，按下 `Ctrl + K V` 快捷键后即可显示与编辑。
- 按下 `Shift + Ctrl + P` 后执行 `Typst: Export the currently open file as PDF` 即可导出 PDF 文件。


## 效果


![](materials/resume.jpg)



## 示例

你可以使用 **简洁** 与 **组合式** 的语法出美观的效果.

```typst
// 设置简历选项与头部
#show: resume.with(
  // 字体基准大小
  size: 10pt,
  // 标题颜色
  themeColor: themeColor,
  // 控制纸张的边距
  top: 1.5cm,
  bottom: 2cm,
  left: 2cm,
  right: 2cm,
  // 如果不需要头像，则将下面的参数注释或删除
  photograph: "profile.jpg",
  photographWidth: 10em,
  gutterWidth: 2em,
)[

= 方橙

#info(
  color: themeColor,
  (
    // 其实 icon 也可以直接填字符串, 如 "fa-phone.svg" 
    icon: faPhone,
    content: "(+86) 155-5555-5555"
  ),
  (
    icon: faBuildingColumns,
    content: "南京大学",
  ),
  (
    icon: faGraduationCap,
    content: "人工智能",
  ),
  (
    icon: faEnvelope,
    content: "orangex4@qq.com",
    link: "mailto:orangex4@qq.com"
  ),
  (
    icon: faGithub,
    content: "github.com/orangex4",
    link: "https://github.com/orangex4",
  ),
)

#h(2em)  // 手动顶行, 2em 代表两个字的宽度
我是 OrangeX4，你也可以叫我 *一只方橙* 或 *方橙*。
现在是南京大学人工智能学院 2020 级本科生，正深陷于学习数学、编程和英语的无边苦海中。
你问为什么我的名字那么奇怪？ 大概是我喜欢吃橘子和橙子，又谐音方程，还有和我的名字谐音的缘故吧。
喜欢一切新奇的东西，兴趣十分广泛。

]
```

以及每一个块

```typst
== #faGraduationCap 教育背景

#sidebar(withLine: true, sideWidth: 12%)[
  2023.05
  
  2020.09
][
  *南京大学* · 人工智能学院 · 人工智能专业
  
  GPA: 4.48 / 5 · Rank: 15%
]
```

```typst
== #faCode 项目经历

#item(
  link(
    "https://github.com/OrangeX4/Latex-Sympy-Calculator",
    [ *Latex Sympy Calculator* ]
  ),
  [ *个人项目* ],
  date[ 2021 年 02 月 – 2021 年 04 月 ]
)

#tech[ NodeJS, Python, VS Code ]

一个用于在 VS Code 中使用 LaTeX 数学公式进行「科学计算」的插件

- 使用 ANTLR 将 LaTeX 语句编译为 Sympy 语句
- 通过 Flask 搭建本地 HTTP 服务器与 VS Code 插件进行通信
- 可以进行多种类型的科学计算，如积分求导、矩阵计算、无穷级数计算等
```