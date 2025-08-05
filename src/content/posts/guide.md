---
title: Fuwari博客模板的综合指南
published: 2024-05-01
description: 这是一个关于Fuwari博客模板的综合指南，涵盖了Markdown的各种功能、视频嵌入、草稿管理和Expressive Code的使用。
tags: [Markdown, Blogging, Demo, Fuwari, Guide, Example, Video, Customization]
category: '写作'
draft: false
image: "./cover.jpeg"
---

# Fuwari博客模板的综合指南

本指南汇集了Fuwari博客模板的多个方面，包括Markdown的基础和扩展功能、如何嵌入视频、管理草稿，以及Expressive Code的代码高亮和代码块特性。

---

## 一、Markdown示例

### 原始Markdown功能

这是一个简单的Markdown博客文章示例。

# An h1 header

段落之间用空行分隔。

第二段。*斜体*、**粗体**和`等宽字体`。列表项看起来像：

- 这一项
- 那一项
- 另一项

请注意，不考虑星号，实际文本内容从第4列开始。

> 块引用是
> 这样写的。
>
> 它们可以跨越多个段落，
> 如果你喜欢。

使用3个破折号表示一个长破折号。使用2个破折号表示范围（例如，“在第12--14章中”）。三个点...将转换为省略号。支持Unicode。☺

## An h2 header

这是一个编号列表：

1. 第一个项目
2. 第二个项目
3. 第三个项目

再次注意，实际文本从第4列开始（从左侧4个字符）。这是一个代码示例：

    # 让我重申...
    for i in 1 .. 10 { do-something(i) }

正如你可能猜到的，缩进4个空格。顺便说一句，除了缩进块，你也可以使用分隔块，如果你喜欢：

```
define foobar() {
    print "Welcome to flavor country!";
}
```

（这使得复制和粘贴更容易）。你可以选择标记分隔块，以便Pandoc进行语法高亮：

```python
import time
# 快速，数到十！
for i in range(10):
    # （但不要“太”快）
    time.sleep(0.5)
    print i
```

### An h3 header

现在是一个嵌套列表：

1. 首先，准备这些食材：

    - 胡萝卜
    - 芹菜
    - 小扁豆

2. 烧开一些水。

3. 把所有东西都倒进锅里，然后按照
    这个算法：

        找到木勺
        打开锅盖
        搅拌
        盖上锅盖
        小心翼翼地把木勺放在锅柄上
        等待10分钟
        回到第一步（或完成后关掉炉子）

    不要碰到木勺，否则它会掉下来。

再次注意，文本始终与4空格缩进对齐（包括上面继续项目3的最后一行）。

这里有一个[网站链接](http://foo.bar)，一个[本地文档链接](local-doc.html)，以及一个[当前文档中的节标题链接](#an-h2-header)。这里有一个脚注[^1]。

[^1]: 脚注文本在这里。

## 表格

表格可以像这样：

| size | material | color     |
| :--- | :------- | :-------- |
| 9    | leather  | brown     |
| 10   | hemp     | canvas    |
| 11   | glass    | transparent |

Table: 鞋子、它们的尺寸和材质

（以上是表格的标题。）Pandoc 还支持多行表格：

| keyword | text                            |
| :------ | :------------------------------ |
| red     | Sunsets, apples, and            |
|         | other red or reddish            |
|         | things.                         |
| green   | Leaves, grass, frogs            |
|         | and other things it's           |
|         | not easy being.                 |



这是一个定义列表：

apples
:   Good for making applesauce.

oranges
:   Citrus!

tomatoes
:   There's no "e" in tomatoe.

同样，文本缩进4个空格。（在每个术语/定义对之间留一个空行，以便更宽松。）

这是一个“行块”（在标准的 Markdown 中，通常使用引用块 `>` 或列表项来模拟行块的效果。这里我使用引用块来表示，因为这更接近“行块”的含义，或者直接使用列表项）：

> Line one
> Line too
> Line tree


图片可以这样指定：

```md
[//]: # (![example image]&#40;./demo-banner.png "An exemplary image"&#41;)
```

内联数学方程式像这样：$\omega = d\phi / dt$。显示数学应该独立成行，并用双美元符号括起来：

$$I = \int \rho R^{2} dV$$

$$
\begin{equation*}
\pi
=3.1415926535
 \;8979323846\;2643383279\;5028841971\;6939937510\;5820974944
 \;5923078164\;0628620899\;8628034825\;3421170679\;\ldots
\end{equation*}
$$

请注意，你可以用反斜杠转义任何你希望字面显示标点符号，例如：\`foo\`、\*bar\*等。

---

## 二、Markdown扩展功能

### GitHub仓库卡片
你可以添加动态卡片链接到GitHub仓库，页面加载时，仓库信息会从GitHub API拉取。

::github{repo="Fabrizz/MMM-OnSpotify"}

使用代码`::github{repo="<owner>/<repo>"}`创建GitHub仓库卡片。

```markdown
::github{repo="saicaca/fuwari"}
```

### 提示框

支持以下类型的提示框：`note` `tip` `important` `warning` `caution`

:::note
突出显示用户即使在浏览时也应考虑的信息。
:::

:::tip
帮助用户更成功的可选信息。
:::

:::important
用户成功所需的重要信息。
:::

:::warning
由于潜在风险，需要用户立即关注的关键内容。
:::

:::caution
某一行动的负面潜在后果。
:::

#### 基本语法

```markdown
:::note
突出显示用户即使在浏览时也应考虑的信息。
:::

:::tip
帮助用户更成功的可选信息。
:::
```

#### 自定义标题

提示框的标题可以自定义。

:::note[我的自定义标题]
这是一个带有自定义标题的提示。
:::

```markdown
:::note[我的自定义标题]
这是一个带有自定义标题的提示。
:::
```

#### GitHub语法

> [!TIP]
> [GitHub语法](https://github.com/orgs/community/discussions/16925)也支持。

```
> [!NOTE]
> GitHub语法也支持。

> [!TIP]
> GitHub语法也支持。
```

---

## 三、文章中包含视频

只需从YouTube或其他平台复制嵌入代码，并将其粘贴到markdown文件中。

```yaml
---
title: 在文章中包含视频
published: 2023-10-19
// ...
---

<iframe width="100%" height="468" src="https://www.youtube.com/embed/5gIf0_xpFPI?si=N1WTorLKL0uwLsU_" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
```

### YouTube

<iframe width="100%" height="468" src="https://www.youtube.com/embed/5gIf0_xpFPI?si=N1WTorLKL0uwLsU_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### Bilibili

<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1fK4y1s7Qf&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

---

## 四、草稿示例

# 这篇文章是草稿

本文目前处于草稿状态，尚未发布。因此，它不会向普通读者可见。内容仍在完善中，可能需要进一步的编辑和审查。

当文章准备好发布时，你可以在Frontmatter中将“draft”字段更新为“false”：

```markdown
---
title: 草稿示例
published: 2024-01-11T04:40:26.381Z
tags: [Markdown, Blogging, Demo]
category: Examples
draft: false
---
```

---

## 五、Expressive Code示例

这里，我们将探讨[Expressive Code](https://expressive-code.com/)中的代码块如何显示。提供的示例基于官方文档，你可以查阅以获取更多详细信息。

### Expressive Code

#### 语法高亮

[语法高亮](https://expressive-code.com/key-features/syntax-highlighting/)

##### 常规语法高亮

```js
console.log('这段代码是语法高亮的！')
```

##### 渲染ANSI转义序列

```ansi
ANSI颜色：
- 常规： [31m红色 [0m [32m绿色 [0m [33m黄色 [0m [34m蓝色 [0m [35m品红 [0m [36m青色 [0m
- 粗体： [1;31m红色 [0m [1;32m绿色 [0m [1;33m黄色 [0m [1;34m蓝色 [0m [1;35m品红 [0m [1;36m青色 [0m
- 柔和： [2;31m红色 [0m [2;32m绿色 [0m [2;33m黄色 [0m [2;34m蓝色 [0m [2;35m品红 [0m [2;36m青色 [0m

256种颜色（显示颜色160-177）：
 [38;5;160m160  [38;5;161m161  [38;5;162m162  [38;5;163m163  [38;5;164m164  [38;5;165m165 [0m
 [38;5;166m166  [38;5;167m167  [38;5;168m168  [38;5;169m169  [38;5;170m170  [38;5;171m171 [0m
 [38;5;172m172  [38;5;173m173  [38;5;174m174  [38;5;175m175  [38;5;176m176  [38;5;177m177 [0m

全RGB颜色：
 [38;2;34;139;34m森林绿 - RGB(34, 139, 34) [0m

文本格式： [1m粗体 [0m [2m柔和 [0m [3m斜体 [0m [4m下划线 [0m
```

#### 编辑器和终端框架

[编辑器和终端框架](https://expressive-code.com/key-features/frames/)

##### 代码编辑器框架

```js title="my-test-file.js"
console.log('标题属性示例')
```

---

```html
<!-- src/content/index.html -->
<div>文件名注释示例</div>
```

##### 终端框架

```bash
echo "这个终端框架没有标题"
```

---

```powershell title="PowerShell终端示例"
Write-Output "这个有标题！"
```

##### 覆盖框架类型

```sh frame="none"
echo "看啊，没有框架！"
```

---

```ps frame="code" title="PowerShell Profile.ps1"
# 如果不覆盖，这将是一个终端框架
function Watch-Tail { Get-Content -Tail 20 -Wait $args }
New-Alias tail Watch-Tail
```

#### 文本和行标记

[文本和行标记](https://expressive-code.com/key-features/text-markers/)

##### 标记整行和行范围

```js {1, 4, 7-8}
// 行1 - 由行号指定
// 行2
// 行3
// 行4 - 由行号指定
// 行5
// 行6
// 行7 - 由范围“7-8”指定
// 行8 - 由范围“7-8”指定
```

##### 选择行标记类型（mark, ins, del）

```js title="line-markers.js" del={2} ins={3-4} {6}
function demo() {
  console.log('这行被标记为已删除')
  // 这行和下一行被标记为已插入
  console.log('这是第二行插入的行')

  return '这行使用中性默认标记类型'
}
```

##### 为行标记添加标签

```jsx {"1":5} del={"2":7-8} ins={"3":10-12}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}
  value={value}
  className={buttonClassName}
  disabled={disabled}
  active={active}
>
  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```

##### 在单独的行上添加长标签

```jsx {"1. 在这里提供value属性:":5-6} del={"2. 移除disabled和active状态:":8-10} ins={"3. 添加这段代码以在按钮内部渲染子元素:":12-15}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}

  value={value}
  className={buttonClassName}

  disabled={disabled}
  active={active}
>

  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```

##### 使用类似diff的语法

```diff
+这行将被标记为已插入
-这行将被标记为已删除
这是一行常规行
```

---

```diff
--- a/README.md
+++ b/README.md
@@ -1,3 +1,4 @@
+这是一个实际的diff文件
-所有内容将保持不变
也不会移除任何空白
```

##### 将语法高亮与类似diff的语法结合

```diff lang="js"
  function thisIsJavaScript() {
    // 整个代码块都将作为JavaScript高亮显示，
    // 而且我们仍然可以为其添加diff标记！
-   console.log('要移除的旧代码')
+   console.log('全新闪亮的代码！')
  }
```

##### 标记行内的单个文本

```js "给定文本"
function demo() {
  // 标记行内的任何给定文本
  return '支持给定文本的多个匹配项';
}
```

##### 正则表达式

```ts /ye[sp]/
console.log('单词yes和yep将被标记。')
```

##### 转义正斜杠

```sh /\/ho.*\//
echo "Test" > /home/test.txt
```

##### 选择内联标记类型（mark, ins, del）

```js "return true;" ins="inserted" del="deleted"
function demo() {
  console.log('这些是插入和删除的标记类型');
  // return语句使用默认标记类型
  return true;
}
```

### 自动换行

[自动换行](https://expressive-code.com/key-features/word-wrap/)

#### 按块配置自动换行

```js wrap
// 带有wrap的示例
function getLongString() {
  return '这是一个非常长的字符串，除非容器非常宽，否则它很可能无法适应可用空间'
}
```

---

```js wrap=false
// 带有wrap=false的示例
function getLongString() {
  return '这是一个非常长的字符串，除非容器非常宽，否则它很可能无法适应可用空间'
}
```

#### 配置换行行的缩进

```js wrap preserveIndent
// 带有preserveIndent（默认启用）的示例
function getLongString() {
  return '这是一个非常长的字符串，除非容器非常宽，否则它很可能无法适应可用空间'
}
```

---

```js wrap preserveIndent=false
// 带有preserveIndent=false的示例
function getLongString() {
  return '这是一个非常长的字符串，除非容器非常宽，否则它很可能无法适应可用空间'
}
```

## 可折叠部分

[可折叠部分](https://expressive-code.com/plugins/collapsible-sections/)

```js collapse={1-5, 12-14, 21-24}
// 所有这些样板设置代码都将折叠
import { someBoilerplateEngine } from '@example/some-boilerplate'
import { evenMoreBoilerplate } from '@example/even-more-boilerplate'

const engine = someBoilerplateEngine(evenMoreBoilerplate())

// 这部分代码将默认可见
engine.doSomething(1, 2, 3, calcFn)

function calcFn() {
  // 你可以有多个折叠部分
  const a = 1
  const b = 2
  const c = a + b

  // 这将保持可见
  console.log(`计算结果： ${a} + ${b} = ${c}`)
  return c
}

// 直到代码块末尾的所有这些代码将再次折叠
engine.closeConnection()
engine.freeMemory()
engine.shutdown({ reason: '示例样板代码结束' })
```

## 行号

[行号](https://expressive-code.com/plugins/line-numbers/)

### 按块显示行号

```js showLineNumbers
// 这个代码块将显示行号
console.log('来自第2行的问候！')
console.log('我在第3行')
```

---

```js showLineNumbers=false
// 这个代码块的行号被禁用
console.log('你好？')
console.log('抱歉，你知道我在哪一行吗？')
```

### 更改起始行号

```js showLineNumbers startLineNumber=5
console.log('来自第5行的问候！')
console.log('我在第6行')
```

---

## 六、Fuwari博客模板的简单指南

> 封面图片来源：[Source](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/208fc754-890d-4adb-9753-2c963332675d/width=2048/01651-1456859105-(colour_1.5),girl,_Blue,yellow,green,cyan,purple,red,pink,_best,8k,UHD,masterpiece,male%20focus,%201boy,gloves,%20ponytail,%20long%20hair,.jpeg)

这个博客模板是使用[Astro](https://astro.build/)构建的。对于本指南中未提及的内容，你可以在[Astro文档](https://docs.astro.build/)中找到答案。

### 文章的Front-matter

```yaml
---
title: 我的第一篇博客文章
published: 2023-09-09
description: 这是我的新Astro博客的第一篇文章。
image: ./cover.jpg
tags: [Foo, Bar]
category: Front-end
draft: false
---
```

| 属性        | 描述                                                                                                                                                                                             |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `title`     | 文章标题。                                                                                                                                                                                       |
| `published` | 文章发布日期。                                                                                                                                                                                   |
| `description` | 文章的简短描述。显示在索引页上。                                                                                                                                                           |
| `image`     | 文章的封面图片路径。<br/>1. 以`http://`或`https://`开头：使用网络图片<br/>2. 以`/`开头：用于`public`目录中的图片<br/>3. 没有前缀：相对于markdown文件 |
| `tags`      | 文章的标签。                                                                                                                                                                                     |
| `category`  | 文章的类别。                                                                                                                                                                                     |
| `draft`     | 如果这篇文章仍是草稿，则不会显示。                                                                                                                                                               |

### 文章文件的存放位置

你的文章文件应该放在`src/content/posts/`目录下。你也可以创建子目录，以便更好地组织你的文章和资产。

```
src/content/posts/
├── post-1.md
└── post-2/
    ├── cover.png
    └── index.md
```