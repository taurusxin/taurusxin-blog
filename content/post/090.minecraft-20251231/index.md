---
title: "【Minecraft】我的高版本 MC 必备的核心套件"
categories: [ "Minecraft" ]
tags: [ "mod", "fabric" ]
draft: false
slug: "minecraft-mods"
date: "2025-12-31T13:37:00+0800"
---

## 所有的一切

首先感谢各位能够看待这篇文章，其实最初写于 2025 年 12 月 31 日，也就是 2025 年的最后一天，但是当时由于种种原因最终这篇文章没有发布出来，拖到了今天（6月17日），所以今天打算把这篇文章完结并且发布出来，工作实在太忙还请见，以下是正文。

---

## 前言

众所周知，我是一个 MC 老玩家了，从 beta 时代开始就入坑了，陪伴我多年的游戏也在一轮轮的迭代中更新出了许多玩法。

今天也是 2025 年最后一天，那么就来讲讲我在现在 Minecraft 高版本（截止今天 20251231，最新版为 1.21.11）的一些必备的工具、模组、材质、光影吧。

## 启动器

### 旋律的时代

绝大多数国内玩家接触 MC 应该是从忘却的旋律开始的，那时候家喻户晓的旋律启动器可谓是经典中的经典，也是将 MC 这个游戏在国内发扬光大。

![xuanlv-launcher](https://cdn.taurusxin.com/hugo/2025/12/31/xuanlv-launcher.webp)

因为当时的官方启动器又丑，下载源还不在国内，想要在国内下载和启动一个游戏可谓难上加难。

然而，旋律启动器内置了加速下载源，还开创了超前的版本隔离概念，为后来居上的启动器提供了版本管理新模式。

遗憾的是，旋律启动器的作者在 2014 年 9 月更新了最后一版后就隐退了，最后支持的版本也就到 1.13 的第 32 个快照。但那时正值 Minecraft 的巅峰时期版本 1.12

### HMCL 与 PCL

直到后来 HMCL 以及 PCL 的出现，正式打开了现代启动器的大门。

![HMCL 启动器](https://cdn.taurusxin.com/hugo/2025/12/31/hmcl.webp)

内置了 Forge，Fabric 等模组加载器以及 OptiFine 的一键安装，以及现在的版本支持从 CurseForge 或者 modrinth 下载、管理模组

### MultiMC

其实在早期，我也使用过一段时间的 HMCL，但是操作还是有点繁琐，后面我发现了一个国外大神开发的 `MultiMC`

![MultiMC 5](https://cdn.taurusxin.com/hugo/2025/12/31/multimc5.png)

支持从远古到快照的多个版本管理，可以将多个示例区分文件夹以及图标，长期以来一直是我首选的启动器，且仅支持正版登录。

### Prism Launcher

后来，我发现每一次都要去 CurseForge （那时候还没有 modrinth）手动下载和更新模组，显得特别麻烦，于是 `Prism Launcher`诞生了，这是一个 MultiMC 的分支，支持 MultiMC 所有特性的情况下，集成了现在的模组管理功能，下面是我自己的多版本启动器截图。

![Prism Launcher](https://cdn.taurusxin.com/hugo/2025/12/31/prism-launcher.png)

Prism Launcher 集成了强大的模组管理能力，支持从 CurseForge 和 modrinth 下载和更新模组，它能够根据你的游戏版本和模组加载器，自动筛选你可以下载的模组，再也不用担心下载错不同加载器或者是不支持游戏版本的模组了（说的就是曾经我想下载 Fabric 的模组，结果全下载了 Forge 的版本……）

![模组管理](https://cdn.taurusxin.com/hugo/2025/12/31/pl-mod-manager.png)

并且支持一键自动更新，以及临时禁用（图中我就把 DH 遥远的地平线临时禁用了）

## 模组

在讲 mod 之前，先谈一谈模组加载器，一直以来 MC 都是 Forge 独一家，直到后面分家后，Fabric 和 NeoForge 的出现让 MC 的生态更加纷繁和混乱，所以自 2018 年 Fabric 出现后，我就一直用的就是它，且下面我要使用的部分必备模组也是 Fabric 独占的。

当前使用的游戏版本是 `1.21.11`（发布时间为 2025/12/9）。此外，请注意，这里只介绍的是在原版的基础上的模组，即没有改变任何游戏玩法、新增游戏内容的模组。

那么就来正式讲讲我都用了些什么模组吧，下面将列出几个表，我将不同用途模组分类到不同的表中，以及他们的用途介绍，部分模组还将详细介绍。

### 画面及游戏优化

| 模组名称                | 用途                                                         |
| :---------------------- | ------------------------------------------------------------ |
| Continuity              | 连接材质，例如无缝玻璃等                                     |
| Distant Horizons        | 非常牛的视距解锁模组，通过自带的 LOD 加载器实现高达 1024 区块视距的震撼游戏画面 |
| Dynamic FPS             | 动态调整游戏 FPS，当焦点离开游戏窗口或者停止不动时降低 FPS 来降低电脑压力 |
| Entity Model Features   | ETF 的扩展，自定义模型                                       |
| Entity Texture Features | 自定义材质和纹理特性                                         |
| EntityCulling           | 隐藏渲染你看不到的实体，增加 FPS                             |
| FerriteCore             | 游戏优化，减少内存占用                                       |
| ImmediatelyFast         | 游戏优化，提高及时渲染性能                                   |
| Iris                    | Fabric 端光影模组                                            |
| LambDynamicLights       | 动态光源                                                     |
| Lithium                 | 必备优化模组锂                                               |
| More Culling            | 性能提升模组                                                 |
| NotEnoughAnimations     | 第三人称下更多的人物动作                                     |
| Packet Fixer            | 防止各种数据包错误                                           |
| Sodium                  | 必备钠模组，增强画面设置                                     |
| Sodium Extra            | 钠模组扩展，更多的画面设置                                   |
| Voxy                    | 新晋视距渲染模组，DH 的替代者                                |

### HUD 与 GUI 增强

| 模组名称            | 用途                               |
| :------------------ | ---------------------------------- |
| 3d-Skin-Layers      | 将玩家的皮肤以 3D 的形式进行渲染   |
| AppleSkin           | 老牌模组，显示当前的饱食度和饱和度 |
| Better Ping Display | 在 Tab 中显示多人玩家的 ping 值    |
| Chat Heads          | 能够在聊天对话框中展示玩家头像     |
| Dynamic Crosshair   | 动态游戏指针                       |
| Inventory HUD +     | 在背包物品栏上直接展示背包内容     |
| Jade                | 显示你看到的是什么内容             |
| Just Enough Items   | JEI 物品管理器，查看合成表等       |
| MiniHUD             | MASA 全家桶必备，迷你 HUD 代替 F3  |
| Show Durability     | 在物品栏直接展示物品剩余耐久       |
| Smooth Scroll       | GUI 平滑滚动                       |
| Smooth Swapping     | 平滑物品移动动画                   |
| Xaero's Minimap     | 展示一个小地图                     |
| Xaero's World Map   | 展示世界地图                       |
| Zoomify             | C 键放大                           |

### 游戏辅助

| 模组名称                | 用途                                           |
| :---------------------- | ---------------------------------------------- |
| Carpet Mod              | 地毯端，强大不用多余解释                       |
| Carpet TIS Addition     | TIS 地毯增强                                   |
| Fast Trading            | 快速村民交易，可以一次交易到村民供货上限       |
| gugle-carpet-addition   | GCA，地毯端的另一个扩展                        |
| Inventory Profiles Next | 强大的物品整理模组                             |
| Item Scroller           | MASA 全家桶必备，物品滚轮                      |
| Litematica              | MASA 全家桶必备，投影                          |
| MaLiLib                 | MASA 全家桶必备前置库                          |
| Syncmatica              | MASA 模组，用于服务器的投影共享                |
| Trade Cycling           | 快速刷新村民交易，不用再打掉工作方块了，半作弊 |
| TweakerMore             | Tweakeroo 的扩展                               |
| Tweakeroo               | 强大的辅助功能模组，半作弊                     |
| Veinminer               | 连锁挖矿，半作弊                               |
| Visible Traders         | 可以直接预见村民的所有未解锁交易，半作弊       |

### 其它

| 模组名称                           | 用途                                                    |
| :--------------------------------- | ------------------------------------------------------- |
| Architectury                       | 一个中间层，多个模组必须的依赖                          |
| Chunky                             | 区块手动加载器，配合 Voxy 使用，DH 官方已经不推荐搭配了 |
| Cloth Config API                   | 一个配置界面的 API                                      |
| Concurrent Chunk Management Engine | 多线程并发的区块加载器，有 OCL 分支支持显卡加速         |
| Fabric API                         | 所有 Fabric 模组必备的核心依赖                          |
| Fabric Language Kotlin             | 模组中使用 Kitlin 语言的支持库                          |
| Mod Menu                           | 必备模组菜单                                            |
| Placeholder API                    | 占位符和文本操作库                                      |
| Silk                               | Kotlin 语言的 MC API                                    |
| YetAnotherConfigLib                | 一个通用配置库                                          |
| libIPN                             | Inventory Profiles Next 的前置                          |

## 光影

现代 Minecraft 的光影基本都是基于 OpenGL Shader 实现的，比较著名的模组有 GLSL Shaders、OptiFine、Iris 等。

下面列出一份表格，展示不同时代下的光影方案和主要加载器。

| 时代 | 光影方案 | 主要加载器 | 代表版本 |
| :-- | :-- | :-- | :-- |
| 1.2.5 以前 | GLSL Shaders | ModLoader | Beta~1.2.5 |
| 1.4.7~1.7.10 | ShadersMod | Forge | 1.4.7~1.7.10 |
| 1.8~1.12.2 | OptiFine Shaders | Forge | 1.8~1.12.2 |
| 1.13~1.16 | OptiFine 时代巅峰 | Forge | 1.13~1.16.5 |
| 1.17~至今 | Iris Shaders | Fabric/NeoForge/Forge | 1.17~1.21+ |

至于光影包，早期时代的巅峰就是 SEUS （Sonic Ether's Unbelievable Shaders），那时候将光影的渲染效果带到了一个新的高度。

后来时代，随着光线追踪技术的发展，光影方案也得到了新的突破，一张表格总结一下。

| 年代 | 代表光影 | 风格 | 搭配材质 | 历史地位 |
| :-- | :-- | :-- | :-- | :-- |
| 2011~2014 | SEUS v1-v10 | 写实 | 原版材质 | Minecraft 第一代光影 |
| 2014~2018 | Chocapic13 | 均衡 | 原版/Soartex | 大量后续光影祖师爷 |
| 2014~2018 | KUDA | 鲜艳 | Sphax | 生存党最爱 |
| 2015~至今 | Sildur's | 风格化 | 原版 | 低配神光影 |
| 2018~至今 | BSL | 色彩电影风 | Vanilla PBR | 现代光影分水岭 |
| 2019~至今 | SEUS PTGI | 路径追踪 | PBR材质 | 光追时代开端 |
| 2020~至今 | Continuum RT | 极致写实 | Stratum | 电影级渲染 |
| 2021~至今 | Complementary | 原版增强 | Complementary PBR | 当前主流 |
| 2022~至今 | Bliss | 超高画质 | PBR材质 | 天空和体积云天花板 |
| 2023~至今 | FastPBR | PBR优化 | LabPBR | PBR普及化 |
| 2024~至今 | IterationRP（ITRP） | 光追写实 | ModernArch/SPBR | 国产光影代表 |

我个人一直搭配使用的是 IterationRP（ITRP）与国产大佬零雾〇五Fogg05的 零雾构想材质包（在此沉痛怀念05大佬，感谢他的贡献）

## 资源包

如果说光影的发展史是：

> SEUS → BSL → PTGI → Complementary
>
那么材质包的发展史基本就是

| 时代 | 代表材质 | 分辨率 | 特点 | 历史地位 |
| :-- | ------------------ | ---------- | ------- | ------------------------- |
| 2009~2012 | Painterly Pack | 16x | 可自定义组合 | 第一代神级材质 |
| 2011~至今 | John Smith Legacy | 32x | 中世纪风格 | RPG玩家必装 |
| 2011~至今 | Faithful | 32x | 原版高清 | 最成功原版增强 |
| 2012~2017 | R3D Craft | 64x~256x | 写实高清 | 第一代HD王者 |
| 2012~至今 | Soartex Fanver | 64x | 柔和卡通 | 整合包标配 |
| 2013~至今 | Sphax PureBDCraft | 64x~512x | 漫画风 | 最火商业材质之一 |
| 2014~至今 | LB Photo Realism | 128x+ | 真实风格 | 写实派代表 |
| 2016~至今 | Vanilla PBR | 16x | PBR增强 | 光影时代开端 |
| 2020~至今 | ModernArch | 128x~1024x | 建筑写实 | 现代豪宅御用 |
| 2021~至今 | Ultimate Immersion | 512x~1024x | 全PBR | 光追时代代表 |
| 2022~至今 | SPBR | 128x | 免费PBR | ITRP常见搭档 |
| 2024~至今 | TruePixelR | 64x~1024x | POM+PBR | 新一代写实材质 |

## 结语

别的不说，Minecraft 这款游戏陪伴了我的整个童年和青春，无数个夜晚与朋友一起挖矿造房子，玩解密，探索新的世界，对我的游戏生涯来说，Minecraft 让我在游戏世界中找到了自己的价值。

祝愿各位玩的开心，另外博主也在筹备一个私有服务器，完全采用独立的硬件和网络，机房和带宽资源已经在和相关公司协调，为的就是给各位提供一个稳定的服务器与游戏环境，所有的后续会更新在评论区，届时欢迎各位报名。
