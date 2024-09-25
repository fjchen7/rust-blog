# 2024 年学习 Rust

_2024 年 9 月 21 日 · #rust · #编程 · #练习_

**目录**
- [2024 年学习 Rust](#2024-年学习-rust)
  - [TL; DR](#tl-dr)
  - [0）参考资料](#0参考资料)
  - [1）阅读 《半小时学会 Rust》](#1阅读-半小时学会-rust)
  - [2）完成 rustlings](#2完成-rustlings)
  - [3）花 10 小时编写 Rust 代码](#3花-10-小时编写-rust-代码)
    - [100 个练习学会 Rust](#100-个练习学会-rust)
    - [Exercism 上的 Rust 课程](#exercism-上的-rust-课程)
    - [Advent of Code](#advent-of-code)
      - [设置](#设置)
      - [2020 年](#2020-年)
      - [2022 年](#2022-年)
    - [教程](#教程)
  - [4）阅读 《常见的 Rust 生命周期误解》](#4阅读-常见的-rust-生命周期误解)
  - [5）再花 10 小时用 Rust 编程](#5再花-10-小时用-rust-编程)
  - [6）阅读 《Rust 标准库特性导览》](#6阅读-rust-标准库特性导览)
  - [接下来做什么？](#接下来做什么)
  - [特别提名](#特别提名)
    - [Tour of Rust](#tour-of-rust)
    - [Comprehensive Rust](#comprehensive-rust)
    - [Rust 模块系统的清晰解释](#rust-模块系统的清晰解释)
  - [讨论](#讨论)
  - [进一步阅读](#进一步阅读)

这是我的个人指南，教你如何从对 Rust 一无所知到尽快达到不错的水平。如果我是今天开始学 Rust，那我也会告诉自己这些东西。

## TL; DR

1. 阅读 [《半小时学会 Rust》](https://fasterthanli.me/articles/a-half-hour-to-learn-rust)（30 - 60 分钟）
2. 完成 [rustlings](https://github.com/rust-lang/rustlings)（2 - 3 小时）
3. 花 10 小时用 Rust 编程（8 - 12 小时）
4. 阅读 [《常见的 Rust 生命周期误解》](./common-rust-lifetime-misconceptions.md)（30 - 60 分钟）
5. 再花 10 小时用 Rust 编程（8 - 12 小时）
6. 阅读 [《Rust 标准库特性导览》](./tour-of-rusts-standard-library-traits.md)（2 - 4 小时）

按这样的过程，经过短短的 19 到 30 小时，你将从 Rust 初学者变成 Rust 高级初学者 😎

## 0）参考资料

学习 Rust 时，建议在浏览器中打开 [Rust by Example](https://doc.rust-lang.org/rust-by-example/index.html) 和 [Rust 标准库文档](https://doc.rust-lang.org/std/)。如果你遇到问题，可以在这两个资源中搜索答案。它们的顶部都有搜索栏，方便你快速查找。

其它不错的选择还有 StackOverflow 和 ChatGPT（或者其它你更喜欢的大型语言模型）。几乎每个 Rust 初学者的问题，都在 StackOverflow 上被提问过并得到回答。它们都可以通过 Google 搜索到。至于 ChatGPT，尽管有一半的时间可能给出错误答案，但至少能为你指明大致方向，让你知道下一步去哪里搜索答案。

如果你尝试了以上所有方式，但仍无法解决问题，那可以去一些适合初学者的 Rust 在线社区：[r/rust](https://www.reddit.com/r/rust/) 子版块，[r/learnrust](https://www.reddit.com/r/learnrust/) 子版块，以及 [官方 Rust 用户论坛](https://users.rust-lang.org/)。

另外，最好在浏览器标签页中打开 [Rust Playground](https://play.rust-lang.org/)。这是一个在线的 Rust 代码编辑器和编译器。它非常适合用来调试小的示例，以巩固你在阅读时学到的知识。

## 1）阅读 [《半小时学会 Rust》](https://fasterthanli.me/articles/a-half-hour-to-learn-rust)

相比其他资源，我更推荐 [《半小时学会 Rust》](https://fasterthanli.me/articles/a-half-hour-to-learn-rust)。它以一种非常系统和循循渐进的方法介绍 Rust 的语法和概念。它从最简单的例子开始，然后在后续的例子中逐渐增加复杂性。这种安排非常符合逻辑，也易于理解。

## 2）完成 [rustlings](https://github.com/rust-lang/rustlings)

[Rustlings](https://github.com/rust-lang/rustlings) 是一组有序的 Rust 编程小练习。每个练习都是一个无法编译或未能通过单元测试的 Rust 小程序。你的任务是修复这些程序，使其能够编译并通过单元测试。

开始 rustlings 之前，你需要安装 Rust。我建议使用 [rustup](https://rustup.rs/) 来管理 Rust 的安装。一旦安装了 `rustup`，你只需要运行 `rustup update`，就可以随时更新你机器上的 Rust。

用 Rust 编程时，你可以使用任何你喜欢的代码编辑器。但我建议使用支持 [rust-analyzer](https://rust-analyzer.github.io/) 的编辑器。我使用 [VS Code](https://code.visualstudio.com/)，并安装了 [这个扩展](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer) 来启用 rust-analyzer。

使用 rustlings 非常简单，可以用 `cargo` 来安装它。Cargo 是 Rust 的依赖管理器和构建工具，随 Rust 一起安装。如果你使用 `rustup` 安装 Rust，那么你也会同时会安装 Cargo。

运行 `cargo install rustlings` 进行安装 rustlings。默认情况下，rustlings 的二进制文件会被放在 `$HOME/.cargo/bin` 中。因此，如果这个路径还不在你的 `$PATH` 变量中，那你应该添加进去，例如：

```sh
export PATH="$HOME/.cargo/bin:$PATH"
```

现在运行 `rustlings`，它将为你创建一个 `rustlings/` 目录，其中包含了所有的练习。在代码编辑器中打开该目录，然后在目录内运行 `rustlings` 命令，并按照其指示操作，它会告诉你应该做哪个练习。完成练习后，命令会告诉你接下来应该做哪个练习。重复这个过程，直到你完成。

## 3）花 10 小时编写 Rust 代码

你可以编写任何内容。但对于你的前 10 小时，我建议使用单线程同步的 Rust。这里面有足够新颖且具有挑战性的 Rust 概念\*，足以让你至少忙上 10 小时。很多人甚至需要更长的时间才能完全理解。多线程异步 Rust 引入了更多复杂概念 \*\*，在基础知识不牢固之前就开始学习，很容易让人感到不知所措。

\*：所有权（ownership）、借用（borrowing）、生命周期（lifetimes）、生命周期省略（lifetime elision）、可变与不可变引用（mutable vs immutable references）、固定大小（sizedness）、解引用强制转换（deref coercion）、特征（traits）、特征对象（trait objects）、泛型（generics）、常量泛型（const generics）、静态与动态分派（static vs dynamic dispatch）、错误处理（error handling）、迭代器（iterators）、模块（modules）、声明宏（declarative macros）、过程宏（procedural macros）...

\*\*：futures、固定（pinning）、轮询（polling）、异步等待（awaiting）、send、sync、取消（cancellation）、流（streams）、sinks、锁（locks）、原子数（atomics）、通道（channels）、actors ...

如果你不知道要编码什么，那么我有一些建议。

### [100 个练习学会 Rust](https://rust-exercises.com/100-exercises/)

如果你喜欢 rustlings 的难度和节奏，那么你会喜欢《100 个练习学会 Rust》（100ELR）。尽管由不同的作者制作，但 100ELR 显然从 rustlings 获得了大量的灵感，更像是后者的延续，。

开始 100 ELR，首先要克隆 [mainmatter/100-exercises-to-learn-rust](https://github.com/mainmatter/100-exercises-to-learn-rust) 仓库到你的机器上，接着使用 `cargo install --locked workshop-runner` 安装测试套件的运行程序，然后就能开始阅读[配套书籍](https://rust-exercises.com/100-exercises/)了。它有 100 章，每章结束时，都会告诉你在仓库中做哪个练习。完成一个练习后，在项目根目录运行 `wr` 来检查你的解答是否通过了单元测试，如果通过了，就继续下一章。重复这个过程，直到你完成所有练习。

尽管听起来有 100 章很多，但它们都很简短，所以你会比想象中更快地完成它们。完成整本书可能需要大多数人大约 15 到 25 小时。

然而，如果你觉得 rustlings 太简单，并且想尝试更具挑战性的东西，那么你可能想要跳过 100ELR。

### Exercism 上的 [Rust 课程](https://exercism.org/tracks/rust)

除了 rustlings 和 100ELR 之外，Exercism 上的 [Rust 课程](https://exercism.org/tracks/rust) 是互联网上最好的 Rust 小练习。它的优秀在于，许多练习是由 Rustaceans 制作的，旨在教你 Rust 相较于其它编程语言的独特之处。有一个练习要求你编写一个声明式宏！甚至有一个练习要求你编写不安全代码！

开始该课程，你需要在 Exercism 上注册一个账户，并加入 Rust 课程（两者都是免费的）。然后，你可以用 Exercism 的在线代码编辑器完成练习，或者将练习下载到你的机器上，使用自己的代码编辑器完成它们，并通过 `exercism` cli 工具将解答提交到 Exercism 上。

我建议使用 `exercism` cli 工具。它有很多优点。首先，你的代码编辑器有 rust-analyzer，而 Exercism 的在线代码编辑器没有。其次，你可以在编辑器中使用暗黑模式，但在 Exercism 上只有付费才能使用（这是高级功能）。第三，你可以使用 git 跟踪你的解答。第四，在编写答案时，你可以选择运行哪些单元测试，而不是每次都运行完整的测试套件。[这里](https://exercism.org/docs/using/solving-exercises/working-locally)是如何在本地机器上进行练习的 Exercism 官方说明。

Exercism 上的每个练习都有一个「学习模式」和「练习模式」。目前，由于 Exercism 团队正在重新设计，Rust 课程的「学习模式」已被禁用。但不管如何，我认为「练习模式」更好，因为它允许你按任意顺序进行练习。虽然现在没有选择，但如果将来 Rust 课程的「学习模式」和「练习模式」重新开放，我建议选择「练习模式」。

虽然 Rust 课程上的练习是按序的，但这个顺序是任意的，是否遵循并不重要。除了 [Luhn](https://exercism.org/tracks/rust/exercises/luhn), [Luhn From](https://exercism.org/tracks/rust/exercises/luhn-from), 和 [Luhn Trait](https://exercism.org/tracks/rust/exercises/luhn-trait) 练习外，所有其他练习都彼此无关，可以按任何顺序完成。

完成练习后最好的地方，是能浏览和点赞其他人的解答。我建议完成练习后看看它们，尤其是那些点赞最多的解答。它们可以教你一些你没有发现的 Rust 惯用写法。

练习按难度分为：简单、中等和困难。目前 Rust 课程共有 99 个练习，我认为有 30 个左右非常好，其他的 59 个只是从其他课程中复制粘贴过来的普通练习。完成整个课程的人占比不到0.1%。如果完成一半的人不到1%，我也丝毫不会吃惊。我已经完成了所有练习。考虑到你可能不会完成所有练习，所以我将推荐我认为最好的那些。

你应该从简单练习开始。难度方面，它们比你在 rustlings 或 100ELR 中的微具挑战性。质量方面，它们都还不错，完成任何一个简单练习都不会超过 20 分钟。另外，如果完成简单练习不再让你感到有收获，那就转到中等练习。不要强迫自己完成所有的简单练习。

就中等难度而言，以下是我个人认为的最好练习（排名不分先后）：

- [PaaS I/O](https://exercism.org/tracks/rust/exercises/paasio)
- [Simple Linked List](https://exercism.org/tracks/rust/exercises/simple-linked-list)
- [Fizzy](https://exercism.org/tracks/rust/exercises/fizzy)
- [Parallel Letter Frequency](https://exercism.org/tracks/rust/exercises/parallel-letter-frequency)
- [Macros](https://exercism.org/tracks/rust/exercises/macros)
- [Robot Name](https://exercism.org/tracks/rust/exercises/robot-name)
- [Triangle](https://exercism.org/tracks/rust/exercises/triangle)
- [Robot Simulator](https://exercism.org/tracks/rust/exercises/robot-simulator)
- [Accumulate](https://exercism.org/tracks/rust/exercises/accumulate)
- [Word Count](https://exercism.org/tracks/rust/exercises/word-count)
- [Grep](https://exercism.org/tracks/rust/exercises/grep)
- [Luhn](https://exercism.org/tracks/rust/exercises/luhn)
- [Luhn From](https://exercism.org/tracks/rust/exercises/luhn-from)
- [Luhn Trait](https://exercism.org/tracks/rust/exercises/luhn-trait)
- [Clock](https://exercism.org/tracks/rust/exercises/clock)
- [Space Age](https://exercism.org/tracks/rust/exercises/space-age)
- [Sublist](https://exercism.org/tracks/rust/exercises/sublist)
- [Binary Search](https://exercism.org/tracks/rust/exercises/binary-search)
- [ETL](https://exercism.org/tracks/rust/exercises/etl)
- [Grade School](https://exercism.org/tracks/rust/exercises/grade-school)
- [Hamming](https://exercism.org/tracks/rust/exercises/hamming)
- [Isogram](https://exercism.org/tracks/rust/exercises/isogram)
- [Nucleotide Count](https://exercism.org/tracks/rust/exercises/nucleotide-count)

根据你选择的练习，完成时间可能需要 10 到 45 分钟。

当你准备好再次提高难度时，以下是我认为最好的困难练习（排名不分先后）：

- [Xorcism（异或密码）](https://exercism.org/tracks/rust/exercises/xorcism)
- [React（响应式系统）](https://exercism.org/tracks/rust/exercises/react)
- [Circular Buffer（环形缓冲区）](https://exercism.org/tracks/rust/exercises/circular-buffer)
- [Forth（Forth语言解释器）](https://exercism.org/tracks/rust/exercises/forth)
- [Doubly Linked List（双向链表）](https://exercism.org/tracks/rust/exercises/doubly-linked-list)

根据你选择的练习，完成时间可能需要 30 到 90 分钟。

如果你做了很多简单练习，加上我推荐的中等和困难练习，你可能需要大约 20 小时。我认为完成整个轨道可能需要双倍的时间，大约 40 小时。话虽如此，如果你开始失去兴趣，不要强迫自己完成整个轨道，最好改变方向，继续你的 Rust 编程之旅，尝试下一件有趣的事情，因为你在学习的同时保持乐趣是最重要的。

完成一系列简单练习，再加上我推荐的中等和困难练习，大概会花费约20小时。完成整个课程可能需要两倍的时间，约40小时。话虽如此，如果你觉得自己开始失去兴趣，就不要勉强自己完成整个课程。此时最好调整方向，尝试 Rust 的其它东西。在学习过程中保持乐趣，是重要的事情。

### [Advent of Code](https://adventofcode.com/)

[Advent of Code](https://adventofcode.com/) (AoC) 是一组编程谜题。自 2015 年起，每年从 12 月 1 日到 25 日，每天都会发布一个新的谜题，每个谜题有两个部分。每年的前 10-15 个谜题往往是简单或中等难度，最后 10-15 个谜题通常很难。谜题被设计成与语言无关，意味着你可以使用任何编程语言来解决。如果你的目标是学习 Rust，那么仅完成谜题并不会给你太多帮助。但如果完成一个谜题后，再查看一位经验丰富的 Rustacean 的解决方案，就可能会帮你学到 Rust 的很多知识。

在这里，这位经验丰富的 Rustacean 就是 fasterthanlime。他不仅发布了 2020 年和 2022 年 AoC 谜题的解答，还写了一些面向初学者的博客文章，解释每个谜题的解决思路。如果你打算通过 AoC 学习 Rust，那么你应该从 2020 年的谜题开始，在完成每个谜题后，阅读 fasterthanlime 相应的博客文章。无论是哪一年，我都不建议做第 10 个之后的谜题，因为它们可能会变得极具挑战性，你会绞尽脑汁，花费大部分时间去想如何解决问题，而不是学习 Rust。

#### 设置

首先，在 [AoC](https://adventofcode.com/) 上创建一个账号。其次，由于 AoC 与语言无关，你必须设置你自己的 cargo 项目并搭建脚手架来解决这些谜题。这样做可能非常有教育意义，但也相当枯燥。我建议跳过这一步，使用这个 Github 模板：[fspoettel/advent-of-code-rust](https://github.com/fspoettel/advent-of-code-rust)：点击 `Use this template` -> `Create a new repository`，然后 `git clone` 克隆仓库到你的机器上。在 `.cargo/config.toml` 中将 `AOC_YEAR` 设置为 `2020`。

你还可以安装 `aoc-cli` 工具，从你的 AoC 账户获取所有说明和输入。为此，要运行 `cargo install aoc-cli --version 0.12.0`，然后创建文件 `$HOME/.adventofcode.session`，并将你的 AoC 的 cookie 粘贴进去。要获取 cookie，需要在 AoC 网站的任何地方，按 `F12` 打开浏览器开发者工具，然后在 `Application` 或 `Storage` 选项卡下找到 `Cookies`，复制 `session` cookie 的值。

完成这些步骤后，你可以在项目目录中运行 `cargo download {day}`，生成脚手架并下载当天的谜题。一旦你认为你已经完成，就可以运行 `cargo solve {day}`，通过 AoC 网站提交解答并进行验证。例如，对于第 1 天，命令将是 `cargo download 1` 和 `cargo solve 1`。

#### 2020 年

正如前面提到的，一定要在 `.cargo/config.toml` 中将 `AOC_YEAR` 设置为 `2020`。完成一个谜题后，去阅读 fasterthanlime 在他的博客上发布的解决方案。这是他前 10 个谜题解决方案的链接：

1. [AoC 2020 Day 1](https://fasterthanli.me/series/advent-of-code-2020/part-1)
2. [AoC 2020 Day 2](https://fasterthanli.me/series/advent-of-code-2020/part-2)
3. [AoC 2020 Day 3](https://fasterthanli.me/series/advent-of-code-2020/part-3)
4. [AoC 2020 Day 4](https://fasterthanli.me/series/advent-of-code-2020/part-4)
5. [AoC 2020 Day 5](https://fasterthanli.me/series/advent-of-code-2020/part-5)
6. [AoC 2020 Day 6](https://fasterthanli.me/series/advent-of-code-2020/part-6)
7. [AoC 2020 Day 7](https://fasterthanli.me/series/advent-of-code-2020/part-7)
8. [AoC 2020 Day 8](https://fasterthanli.me/series/advent-of-code-2020/part-8)
9. [AoC 2020 Day 9](https://fasterthanli.me/series/advent-of-code-2020/part-9)
10. [AoC 2020 Day 10](https://fasterthanli.me/series/advent-of-code-2020/part-10)

#### 2022 年

如果你已经完成了至少 10 个 2020 年的谜题，那么推荐接下来做 2022 年的谜题。再克隆一份 [fspoettel/advent-of-code-rust](https://github.com/fspoettel/advent-of-code-rust)，并在 `.cargo/config.toml` 中将 `AOC_YEAR` 设置为 `2022`。这是 fasterthanlime 对 2022 年谜题的解答的链接：

1. [AoC 2022 Day 1](https://fasterthanli.me/series/advent-of-code-2022/part-1)
2. [AoC 2022 Day 2](https://fasterthanli.me/series/advent-of-code-2022/part-2)
3. [AoC 2022 Day 3](https://fasterthanli.me/series/advent-of-code-2022/part-3)
4. [AoC 2022 Day 4](https://fasterthanli.me/series/advent-of-code-2022/part-4)
5. [AoC 2022 Day 5](https://fasterthanli.me/series/advent-of-code-2022/part-5)
6. [AoC 2022 Day 6](https://fasterthanli.me/series/advent-of-code-2022/part-6)
7. [AoC 2022 Day 7](https://fasterthanli.me/series/advent-of-code-2022/part-7)
8. [AoC 2022 Day 8](https://fasterthanli.me/series/advent-of-code-2022/part-8)
9. [AoC 2022 Day 9](https://fasterthanli.me/series/advent-of-code-2022/part-9)
10. [AoC 2022 Day 10](https://fasterthanli.me/series/advent-of-code-2022/part-10)

### 教程

大多数Rust教程的目标，是向你展示如何用Rust实现某个软件，而不一定是教你Rust语言本身。因此，许多教程作者都假设读者已经对这门语言有一定的了解，为了保持教程的重点和简洁，会省略许多针对初学者的解释。

话虽如此，编写一个有一定难度的软件，比完成一堆小练习要更有趣和更有成就感。所以这种方法可能更适合保持你的学习动力，特别是当你在构建一个你真正感兴趣和兴奋的东西时。

我希望在这里推荐一些教程。但是已经有太多教程，很难一一评估和按质量排名。不过，质量可能并不是那么重要，重要的是你在编写Rust代码并享受这个过程。所以，选择任何看起来有趣的教程并跟着学习，不要过分纠结细节。

不过，我要特别提一下 [Codecrafters](https://codecrafters.io)。他们的教程质量非常高，而且所有教程都提供了 Rust 模板。在每个教程的每一步，他们都会给出指导和提示，告诉你如何实现程序的下一部分。你完成并提交代码后，它就会运行一个测试套件，来检查是否所有内容都正确实现了。

Codecrafters的一个大的缺点是费用，每月要 40 美元。他们偶尔会有促销活动，免费开放某个教程一个月。所以，你在浏览他们网站时，可能会幸运地发现一个你感兴趣的教程是免费的。然而，他们的定价表明，他们的目标是那些希望培训其工程师的软件公司，而不是个人工程师。如果你在这样的公司工作，可以查看你的公司是否为类似Codecrafters的课程提供培训津贴，这样你就可以用这些津贴来支付费用。

## 4）阅读 [《常见的 Rust 生命周期误解》](./common-rust-lifetime-misconceptions.md)

免责声明：这是我写的。

阅读 [《常见的 Rust 生命周期误解》](./common-rust-lifetime-misconceptions.md) 将帮助你理解，为什么在过去的10个小时的Rust编程中，你尝试的一半东西都不起作用 🙂

玩笑归玩笑，理解生命周期可能是许多初学者在学习Rust时遇到的最大绊脚石，这篇文章澄清了关于生命周期的最常见误解，这些误解常常引起人们的困惑和挫败感。

我之所以建议在至少有10小时的Rust编码实践经验后再阅读它，是因为对于纯粹的初学者来说，它这可能包含了过多的技术信息，可能会让人感到不知所措，而不是提供帮助。

## 5）再花 10 小时用 Rust 编程

如果你仍然不知道要编写什么代码，我的建议保仍然是：[100 个练习学会 Rust](https://rust-exercises.com/100-exercises/)，Exercism 上的 [Rust 课程](https://exercism.org/tracks/rust)，[Advent of Code](https://adventofcode.com/)，或其它教程。

此外，现在你已经有了一些Rust经验。如果你喜欢冒险，可以尝试用Rust编写一些多线程异步代码。

## 6）阅读 [《Rust 标准库特性导览》](./tour-of-rusts-standard-library-traits.md)

免责声明：这是我写的。

特征（Trait）是Rust中编写多态代码的主要方式。它们无处不在，尤其是对来自标准库的特征来说。本文对最常见的标准库Trait进行了导览，介绍了它们的方法、如何使用它们以及何时为你的自定义类型实现它们。文章非常彻底，并分享了大量实用的技巧。尽管文章篇幅较长，但你不必读阅读全文就能从中受益，所以不要被它的长度吓到。

## 接下来做什么？

恭喜你！你做到了。你肯定已经掌握了足够的Rust知识，可以自行探索前进的道路。祝你好运并玩得开心。

## 特别提名

这些是我非常喜欢的其他 Rust 初学者资源，但我在我的 Rust 学习指南中找不到它们的位置。

### [Tour of Rust](https://tourofrust.com/)

这是一个非常好的资源。然而，它涉及很多其他资源已经覆盖的内容，所以为了保持指南的简洁性，我没有将其包括在内。

### [Comprehensive Rust](https://google.github.io/comprehensive-rust/)

这是Google的Android团队开发的一门Rust课程。它是一个幻灯片集合，本应由一位具有Rust经验的讲者来讲解，但书籍版本在每页底部有讲者注释，因此可以作为独立资源来学习。

这门课程非常简洁，节奏很快，同时还涵盖了其他初学者资源中通常忽略的Rust部分，例如[裸机 Rust](https://google.github.io/comprehensive-rust/bare-metal.html)和[Rust 中的并发性](https://google.github.io/comprehensive-rust/concurrency/welcome.html)。然而，因为它更适合由讲者来呈现，所以不太适合放入面向自学者的指南中。

### [Rust 模块系统的清晰解释](https://www.sheshbabu.com/posts/rust-module-system/)

这是一篇很棒的文章。我不确定在指南中放在哪里，因为它可以放在任何地方，但理想情况下，当学习者开始将他们的 Rust 代码拆分到多个文件时，它就会出现，这在每个人的 Rust 编程旅程中都有所不同。无论如何，当你的时机到来时，请阅读这篇文章。

这是一篇很棒的文章。我不确定在指南中将它放在哪里，因为它可以放在任何地方。但理想情况下，学习者开始将Rust代码分散到多个文件时，应该阅读这篇文章。在每个人的Rust编码旅程中，这个时间点都会有所不同。无论如何，当你到了那一步时，请阅读这篇文章。

## 讨论

在以下平台讨论本文：

- [Github](https://github.com/pretzelhammer/rust-blog/discussions/84)

## 进一步阅读

- [常见的 Rust 生命周期误解](./common-rust-lifetime-misconceptions.md)
- [Rust 标准库特性导览](./tour-of-rusts-standard-library-traits.md)
- [并发编程初学者指南：使用 Tokio 编写多线程聊天服务器](./chat-server.md)
- [Rust 中的 Sizedness](./sizedness-in-rust.md)
- [同步和异步 Rust 中的 RESTful API](./restful-api-in-sync-and-async-rust.md)
- [通过太多脑子编译器学习汇编语言](./too-many-brainfuck-compilers.md)
