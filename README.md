# Josh's ToolBox

面向朋友聚会、校园活动、课堂练习与娱乐模拟的浏览器小工具集合，包含计分、收银、单词练习、拼音输入和课堂小游戏。

**[打开工具首页](https://joshzhangzzx.top/)** · [问题反馈](https://github.com/JoshZ-zzx/ToolBox/issues)

## 工具导航

| 工具 | 主要用途 | 在线入口 | 源文件 |
| --- | --- | --- | --- |
| 干瞪眼计分器 X beta | 单局结算、累计计分与战绩分享 | [打开](https://joshzhangzzx.top/JustLookX_v2_compact_keypad_selectfix.html) | [HTML](JustLookX_v2_compact_keypad_selectfix.html) |
| 收银记账系统 v4.0 | 商品收银、后厨订单与宣传屏 | [打开](https://joshzhangzzx.top/CashierV4.0.html) | [HTML](CashierV4.0.html) |
| 英语单词矩阵寻宝 | 自定义词库的横纵向找词练习 | [打开](https://joshzhangzzx.top/EngWrdSqrV2.html) | [HTML](EngWrdSqrV2.html) |
| 打字学习小助手 | 看汉字输入拼音、键盘练习 | [打开](https://joshzhangzzx.top/TypingExerciser.html) | [HTML](TypingExerciser.html) |
| 六一快乐糖果雨 | 移动篮子接物品的反应力游戏 | [打开](https://joshzhangzzx.top/61game_1_v1.1.html) | [HTML](61game_1_v1.1.html) |
| 六一知识小火箭 | 数学、语文与常识答题 | [打开](https://joshzhangzzx.top/61game_2_v1.html) | [HTML](61game_2_v1.html) |
| 原神祈愿模拟器 | 角色活动祈愿模拟与资源规划 | [独立版](https://ys.joshzhangzzx.top/) | [独立仓库](https://github.com/JoshZ-zzx/GenshinWishSimulator) |
| 诗文笺 | 高中古诗文注释查询与伴读 | [独立版](https://joshz-zzx.github.io/shiwenjian/) | [独立仓库](https://github.com/JoshZ-zzx/shiwenjian) |

本仓库的单文件工具可通过在线页面使用，也可下载对应 HTML 后用浏览器打开，无需安装应用。下载后的工具首页依赖同目录下的各工具文件。两个独立项目的运行方式以各自仓库说明为准。

## 数据保存

| 工具 | 保存范围 | 备份与导出 |
| --- | --- | --- |
| 干瞪眼计分器 X beta | 当前浏览器中的玩家、设置和已入账流水 | 复制或分享战绩文本，无完整存档导入 |
| 收银记账系统 v4.0 | 当前浏览器中的商品、订单、账本及设置 | JSON 导入导出 |
| 原神祈愿模拟器旧版 v2 | 当前浏览器中的祈愿状态、累计统计与设置 | 预测结果 CSV；另有[存档迁移页](https://joshzhangzzx.top/GenshinMigration.html) |
| 古诗文查询旧版 | 当前浏览器中的收藏、最近查询、自测设置与阅读位置 | 无学习记录导入导出 |
| 单词矩阵、打字练习、两个六一游戏 | 当前页面的临时状态 | 无持久化成绩记录 |

本地记录不自动跨设备、浏览器或域名同步，在线页面与离线文件也不共享存储。清理浏览器数据可能删除记录。独立版与 ToolBox 旧版的数据保存方式和迁移范围见对应项目说明。

## 干瞪眼计分器

[X beta](https://joshzhangzzx.top/JustLookX_v2_compact_keypad_selectfix.html)按剩余手牌、炸弹数和全关状态计算单局分数，支持玩家管理、底分设置、输分封顶、累计排名、流水删除与战绩文本分享。

每局输入各玩家剩余牌数和炸弹总数后，页面展示清算结果；确认入账后更新累计战绩。“小憩”玩家不参与当局结算，“重置全场”清除本场记录。

### 计分规则

- 每个炸弹使倍率翻倍，炸弹倍率为 `2^炸弹数`。
- 剩余 5 张按全关处理，额外乘 2；全关张数不会随发牌规则自动变化。
- 输家扣分 = 剩余牌数 × 底分 × 炸弹倍率 × 全关倍率。
- 启用封顶时，各输家的扣分分别受封顶金额约束。
- 剩余 0 张的玩家获得其他玩家扣分之和；多个玩家填 0 时平分赢分。

例如底分为 1、当局有 1 个炸弹，甲剩 2 张、乙剩 5 张、丙出完，未启用封顶时三人分别为 −4、−20、+24 分。

### 操作与记录

手机窄屏提供底部专用小键盘，包含玩家切换、牌数输入、炸弹增减和结算。电脑端牌数输入框支持 Enter 切换至下一位，最后一位按 Enter 打开结算；`=` 增加炸弹，`-` 减少炸弹。

玩家、设置和已确认入账的流水会本地保存，尚未入账的当局输入不作为完整草稿保存。战绩分享为文本，不是可恢复的存档。

## 收银记账系统

[收银记账系统 v4.0](https://joshzhangzzx.top/CashierV4.0.html)提供收银台、后厨屏和宣传屏，适用于校园游园会、义卖与小型摊位。文件名为 v4.0，页面内部标题和导出数据版本号为 v3.6.4。

| 功能 | 说明 |
| --- | --- |
| 商品与订单 | 商品名称、价格、数量、备注与自定义优惠 |
| 收款展示 | 现金实收与找零计算，微信、支付宝收款码展示 |
| 后厨屏 | 接收订单，按订单号展示制作与完成状态 |
| 宣传屏 | 展示购物车、收款信息、海报或欢迎画面 |
| 今日账本 | 已确认交易与收入汇总 |
| 数据备份 | 商品、购物车、交易、后厨订单、订单号、收款码和宣传设置的 JSON 导入导出 |

订单经“确认收款”后写入账本并发送至后厨。选择电子支付方式只展示二维码，系统不会核验微信或支付宝实际到账状态。

三屏通过同一浏览器的多个窗口协作，适用于一台电脑连接多个显示器；没有跨设备联网订单服务。后厨屏与宣传屏依赖收银台窗口，打开窗口受浏览器弹窗权限影响。

收银台在非文字编辑状态下支持快捷键：S 定位最近商品数量，B 定位备注，Y 添加 1 元优惠；Enter 的作用随输入框和结算阶段变化。

导入 JSON 会覆盖当前业务数据，备份含收款码时另行确认是否覆盖收款码。“清空业务数据”清除商品、交易、购物车和后厨订单，并重置订单号，保留收款码。导出文件可能包含收款码图片，旧版与当前版的导入兼容性未经完整验证。

## 英语单词矩阵寻宝

[英语单词矩阵寻宝](https://joshzhangzzx.top/EngWrdSqrV2.html)将目标单词放入字母矩阵的横向或纵向，支持自定义词库、限时挑战、暂停与重置。

默认词库为 APPLE、BANANA、ORANGE、CHERRY，时间设置为 60 秒。词库接受空格、换行、英文逗号或中文逗号分隔，输入字母会转换为大写。找词采用先点首字母、再点末字母的方式，两个端点需在同一行或同一列。

**已知计时限制：** 初始化、重置或重新应用设置后，倒计时可能停留在初始值；先点“暂停”、再点“继续”可启动计时。设置和挑战进度仅保留在当前页面，刷新后恢复默认。

## 打字学习小助手

[打字学习小助手](https://joshzhangzzx.top/TypingExerciser.html)面向低年级拼音与键盘练习，每轮随机抽取 10 个不重复的汉字。

答案为不带声调的拼音，例如“学”为 `xue`，“绿”为 `lv`。实体键盘输入字母，Backspace 删除，Enter 提交；答对后进入下一题，答错时显示正确拼音并清空输入。页面没有用于唤起手机软键盘的文本输入框。

每次答对得 10 分，连续答对达到 3 次后，每次继续答对额外加 5 分；答错清零连对次数。成绩与进度不持久保存。

## 六一快乐糖果雨

[六一快乐糖果雨](https://joshzhangzzx.top/61game_1_v1.1.html)是一款 60 秒接物游戏，支持左右方向键、鼠标移动与触屏滑动。

| 物品 | 分值 |
| --- | --- |
| 糖果、棒棒糖 | 1 分 |
| 星星、蛋糕、气球 | 2 分 |
| 礼物 | 5 分 |

每连续接住 5 个物品额外获得 3 分，漏接会中断连击。物品下落速度随时间增加，成绩仅用于当前一轮。

## 六一知识小火箭

[六一知识小火箭](https://joshzhangzzx.top/61game_2_v1.html)提供每轮 10 题的答题挑战，包括 5 道百以内加减法、2 道语文题、2 道常识题和 1 道趣味题，题目与选项随机排列。

每题限时 20 秒，支持点击选项或键盘 1、2、3 作答。答对得分为 `10 + 剩余秒数`，答错或超时不得分并显示答案。结束后展示答对题数、总分和称号，不保存历史成绩。

## 独立项目与旧版

### 原神祈愿模拟器

[独立版](https://ys.joshzhangzzx.top/)提供单抽、十连、单 UP 资源回收预测、多个 UP 目标预算规划和完整持久存档导入导出，详见[项目说明](https://github.com/JoshZ-zzx/GenshinWishSimulator#readme)。

本仓库保留[普通 v2](https://joshzhangzzx.top/GenshinSimulator_v2.html)与[图片版](https://joshzhangzzx.top/GenshinSimulator_v2_images.html)。旧版状态可通过[存档迁移页](https://joshzhangzzx.top/GenshinMigration.html)导出，普通版与图片版存档相互独立。旧版没有持久保存的逐抽历史不在迁移范围内，预测 CSV 也不是恢复存档。

模拟结果基于非官方概率模型，仅供体验和资源规划，不会读取真实游戏账号，也不保证实际祈愿结果。

### 诗文笺

[诗文笺](https://joshz-zzx.github.io/shiwenjian/)是高中古诗文注释查询与伴读工具，包含 71 篇课文、2349 条原始注释，支持词义检索、随文注释、同词例句、收藏与释义自测，详见[项目说明](https://github.com/JoshZ-zzx/shiwenjian#readme)。

本仓库保留[单文件旧版](https://joshzhangzzx.top/ClassicalChinese.html)，可下载 [ClassicalChinese.html](ClassicalChinese.html) 离线使用。旧站与独立站的本地学习记录不共享，当前均无学习记录导入导出功能。

教材出版年份、版次与印次尚未确认，内容未经逐条对照纸质教材，完整内容范围与校对说明见页面页脚。

### 其他旧版文件

| 工具 | 文件 |
| --- | --- |
| 干瞪眼计分器 X 经典版 | [JustLookX.html](JustLookX.html) |
| 收银记账系统 v3.5 | [CashierV3.5_layout.html](CashierV3.5_layout.html) |
| 收银记账系统 v3.3 | [CashierV3.3.html](CashierV3.3.html) |
| 原神祈愿模拟器原版 | [GenshinSimulator.html](GenshinSimulator.html) |

## 问题反馈与许可

[GitHub Issues](https://github.com/JoshZ-zzx/ToolBox/issues)用于反馈工具问题与功能需求。工具文件名、设备与浏览器、复现步骤及预期和实际结果有助于定位问题。

本仓库采用 [GPL-3.0 许可证](LICENSE)。
