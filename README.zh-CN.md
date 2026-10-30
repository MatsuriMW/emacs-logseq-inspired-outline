# Emacs Logseq Inspired Outline

[English](./README.md) · **简体中文**

在 Obsidian 里用列表写大纲时的一组编辑改进。

我从 Logseq 搬到 Obsidian，最想念的是 Logseq 把每个列表项当成一个「块」来操作的手感；另一半灵感来自 Emacs（org-mode 的大纲操作）和受 Emacs 影响的大纲软件 Bike——跳到上一级、在同一级的末尾接着写、把几行收成一组，这些都是 Emacs 系大纲编辑里很顺手、Obsidian 却没有的动作。这个插件把它们搬了过来。

> 原名「编辑体验 Logseq 化」（id `esc-select-block`）。

## 受 Logseq 启发

- **Esc 选中整块**：光标在列表里按 Esc，选中这个列表项连同它所有的子项。选中后：
  - ↑ / ↓ 在块之间切换，⇧↑ / ⇧↓ 扩选；
  - Tab / ⇧Tab、⌥↑↓ 挪动之后仍然整块选中；
  - ⌫ 删掉这一块后自动选中下一块；
  - 按一个字母改每块首行的任务关键词：`t` TODO、`d` DOING、`x` DONE、`y` YES、`n` NO、`m` MAYBE、`c` CANCELLED、`w` WAITING，同一个字母再按一次就去掉关键词，子项不动。关键词就是笔记里的文字，装不装任务插件都能用；装了 TODOseq 时也认它设置里的自定义关键词；
  - 别的字打不进去，不会替换掉整块，Enter 回到编辑，再按 Esc 取消选中。
- **成对符号包裹**：选中文字后输入 `(` `[` `"` `「` `《` 等（中英文输入法都行），文字会被包起来而不是被替换；连按两次 `[` 就是双链。包好后按 Enter，光标跳到右半边符号后面接着写。
- **⌘K** 在当前块下面插一条分割线。
- **块类型转换**（⌘\\ 循环）：无序列表 → 有序列表 → 普通段落。有序列表支持 `1. 2. 3.`、论文式 `4.1 4.2`、字母 `a. b. c.`。
- **Shift 点双链在侧边栏打开**：编辑器、阅读视图里都行。双链的右键菜单也多了「在拆分视图中打开」「在侧边栏中打开」（替换掉 Obsidian 自带的「在新标签组中打开」，那一项只在文件存在时才有）。双链指向的笔记还不存在时，打开就自动新建。装了 [Roam Backlinks](https://github.com/MatsuriMW/roam-backlinks) 时，侧边栏用它的叠放，一页接在上一页下面。

## 受 Emacs（及 Bike）启发

- **⌘⌥↑ 跳到母块（go to ancestor）**：跳到上一级列表项，光标停在母块那一行的末尾，可以直接接着写。连按一层层往上；⌘⌥⇧↑ 直接到最顶层。
- **⌘Enter 在同级末尾新建块（create at the same level）**：不管光标在这一组同级块的哪一块上，都在这一组的最后面（最后一块的子项之后）新建一个空的同级块。有序列表会接着编号（`3.` 之后是 `4.`，`4.2` 之后是 `4.3`，`b.` 之后是 `c.`），复选框列表的新块也带 `[ ]`。光标不在列表里时不接管 ⌘Enter。
- **⌘⌥↓ Group rows**：把选中的几块一起降一级，在上面插一个空的母块等你起名。

所有快捷键都可以在 设置 → 快捷键 里搜「Emacs Logseq Inspired Outline」修改（⌘Enter 和 Esc、↑↓ 这类是编辑器键位，固定）。

## 安装

从 [Releases](https://github.com/MatsuriMW/emacs-logseq-inspired-outline/releases) 下载 `main.js`、`manifest.json`，放进库里的 `.obsidian/plugins/emacs-logseq-inspired-outline/`，在 设置 → 第三方插件 里启用。也可以用 BRAT 装：`MatsuriMW/emacs-logseq-inspired-outline`。

## License

MIT
