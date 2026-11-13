# Kim the Pirate（海盗金）汉化说明

## 一、模组信息



* 模组名：Kim the Pirate（金／海盗金）

* 类型：BG2 / ToB 可恋爱 NPC 模组（含 ToB 主线内容）

* 作者：grenouillebleue

* 维护／整合：Roxanne（Baldur's Extended World）

* 版本：V2（tp2 中 `VERSION ~V2~`）

* 语言目录：`KimPirate/English/`（原文，未改动）、`KimPirate/Schinese/`（本汉化）

## 二、汉化范围

本模组属于典型的 **tra 型模组**：所有台词、物品描述、日志全部通过 `@N` 引用，`.d` 对话文件里不内嵌任何台词。因此汉化只落在 tra 与 tp2 上，`.d`、`.baf`、`.cre`、`.itm` 一个字节都没有改动。

### 2.1 tra 文件（15 个，共 2527 条）



| 文件               | 条目数  | 内容                                                                        |
| ---------------- | ---- | ------------------------------------------------------------------------- |
| Banters.tra      | 468  | 队友互聊（明斯克、娜莉亚、瓦里格、维康尼亚、吉野、玛兹、科根、凯尔登、扬・詹森、瑟恩德、爱黎、阿诺门、艾德温、海尔达利、佩图尼亚、贾希拉、爱蒙等） |
| KimInterject.tra | 367  | 主线插话（含伊拉萨拉伏击、波迪、日志 @400）                                                  |
| KimJ.tra         | 1151 | ToB 主线 + 恋爱长线（哲学问答、理想女人调查、星空夜告白、昵称互称）                                     |
| Kim.tra          | 184  | 与主角初见、决斗、雇佣谈判                                                             |
| ImpKim.tra       | 86   | 公园小恶魔祖布祖布／巴兹巴兹与逻辑谜题                                                       |
| Quete.tra        | 70   | 光耀之心骑士团取回骨灰瓮任务                                                            |
| SkullKim.tra     | 57   | 骷髅形态绿胡子                                                                   |
| Setup.tra        | 37   | 人名、物品名／未鉴识描述／鉴定描述、BIO、两条日志                                                |
| Zven.tra         | 28   | 兹文索要面具                                                                    |
| KimSolar.tra     | 24   | ToB 索拉现身警告                                                                |
| Barbe.tra        | 24   | 绿胡子（恶魔）复仇线                                                                |
| UmbKim.tra       | 11   | 安柏丽女祭司娜迪亚                                                                 |
| Barbe3.tra       | 9    | 绿胡子终局                                                                     |
| VampKim.tra      | 9    | 被波迪转化的金                                                                   |
| barbe2.TRA       | 2    | 绿胡子短句                                                                     |

合计 **2527 条**，与英文原文条目数完全一致。

### 2.2 tp2 内嵌文本（已处理，原件备份为 `KimPirate.tp2.bak`）

`KimPirate.tp2` 里 `COPY ~KimPirate/Cre/Kim.cre~` 一段有一批直接写在 tp2 里的 `SAY`（不经过 tra），已一并汉化：



* `SAY NAME1 ~金~` / `SAY NAME2 ~金~`

* `SAY LEADER ~叫我船长~`

* `SAY TIRED ~我需要我的吊床！~`

* `SAY BORED ~我已经在咬指甲了。~`

* `SAY BATTLE_CRY1 ~为船长！~`

* `SAY BATTLE_CRY2 ~尝尝你自己的血！~`

* `SAY DAMAGE ~啊。~`

* `SAY DYING ~该死的蠢货。~`

* `SAY HURT ~来瓶药水就好。~`

* `SAY SELECT_COMMON1 ~快一点~`

* `SAY SELECT_COMMON2 ~什么？~`

* `SAY SELECT_ACTION1 ~已经办好了。~`

* `SAY SELECT_ACTION2 ~是，先生~`

* `SAY CRITICAL_HIT ~就是这个~`

* `SAY CRITICAL_MISS ~该死的魔法~`

* `SAY TARGET_IMMUNE ~该死的魔法~`

* `SAY INVENTORY_FULL ~我不是你的驮骡！~`

### 2.3 tp2 的一处路径修正

原文：



```
ADD_JOURNAL @367 USING ~KimPirate/English/Setup.tra~
```

路径硬编码为 English，选中文语言安装时日志仍会取英文。已改为：



```
ADD_JOURNAL @367 USING ~KimPirate/%LANGUAGE%/Setup.tra~
```

`%LANGUAGE%` 是 WeiDU 的当前语言目录名（此处为 `English` / `schinese`），英文与中文安装都能取到各自语言的日志文本。

## 三、编码与换行



* 全部 15 个 tra：**UTF-8 无 BOM**，**纯 CRLF** 换行（无裸 LF、无 `\r\r`）。

* tp2：UTF-8 无 BOM，纯 CRLF（原文件即为 CRLF，保持）。

* 未使用 `HANDLE_CHARSETS`（原 tp2 本来也没有），按你之前定下的做法：**不做编码转换，直接让 WeiDU 按 UTF-8 读源文件**。EET 版 `lang\zh_CN\dialog.tlk` 为 UTF-8 中文时可直接正常显示。

* 未把任何 tra 转成 ANSI（Alora 的 `LEXER ERROR … invalid character` 就是 ANSI 中文导致的；WeiDU 不会替你自动转码）。

## 四、术语表（主要译名）



| 英文                                                                                                                                                                                           | 译文                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Kim / Kim-Lan                                                                                                                                                                                | 金／金兰                                                                            |
| Kim the Pirate                                                                                                                                                                               | 海盗金                                                                             |
| Greenbeard                                                                                                                                                                                   | 绿胡子                                                                             |
| Priestess Nadia                                                                                                                                                                              | 娜迪亚女祭司                                                                          |
| Solar / Deva                                                                                                                                                                                 | 索拉／迪瓦                                                                           |
| ZubbZubb / BuzzBuzz                                                                                                                                                                          | 祖布祖布／巴兹巴兹                                                                       |
| Zven                                                                                                                                                                                         | 兹文                                                                              |
| Renal Bloodscalp                                                                                                                                                                             | 雷纳尔・血头皮                                                                         |
| Mae'Var                                                                                                                                                                                      | 梅瓦尔                                                                             |
| Illasera                                                                                                                                                                                     | 伊拉萨拉                                                                            |
| Bodhi                                                                                                                                                                                        | 波迪                                                                              |
| Umberlee                                                                                                                                                                                     | 安柏丽（「深渊女王」）                                                                     |
| Irenicus / Joneleth                                                                                                                                                                          | 艾瑞尼卡斯／乔内莱斯（「乔恩」）                                                                |
| Sarevok                                                                                                                                                                                      | 萨瑞沃克                                                                            |
| Gorion                                                                                                                                                                                       | 葛立安                                                                             |
| Candlekeep                                                                                                                                                                                   | 烛堡                                                                              |
| Spellhold                                                                                                                                                                                    | 禁魔监狱                                                                            |
| Athkatla                                                                                                                                                                                     | 阿斯卡特拉                                                                           |
| Baldur's Gate                                                                                                                                                                                | 博德之门                                                                            |
| Brynnlaw                                                                                                                                                                                     | 布林罗                                                                             |
| Copper Coronet                                                                                                                                                                               | 铜冠旅店                                                                            |
| Waukeen's Promenade                                                                                                                                                                          | 沃金步道                                                                            |
| Sea's Bounty                                                                                                                                                                                 | 海之恩赏                                                                            |
| Government district                                                                                                                                                                          | 政府区                                                                             |
| Order of the Radiant Heart                                                                                                                                                                   | 光耀之心骑士团                                                                         |
| Helm                                                                                                                                                                                         | 海姆                                                                              |
| Carsomyr                                                                                                                                                                                     | 卡索米尔                                                                            |
| Vecna                                                                                                                                                                                        | 维克那                                                                             |
| Staff of the Magi                                                                                                                                                                            | 大法师法杖                                                                           |
| Sahuagin                                                                                                                                                                                     | 沙华鱼人                                                                            |
| illithium                                                                                                                                                                                    | 依利希姆                                                                            |
| Aran / Mook                                                                                                                                                                                  | 阿兰／穆克                                                                           |
| Saemon Havarian                                                                                                                                                                              | 塞蒙・哈瓦里安                                                                         |
| Trademeet                                                                                                                                                                                    | 贸易区                                                                             |
| Hendak / Lethinan                                                                                                                                                                            | 亨达克／莱瑟南                                                                         |
| Samia / Adalon / Elhan                                                                                                                                                                       | 萨米亚／阿达隆／艾尔汉                                                                     |
| Solaufein                                                                                                                                                                                    | 索劳芬                                                                             |
| Jarlaxle / Drizzt                                                                                                                                                                            | 贾拉索／崔斯特                                                                         |
| Tashia                                                                                                                                                                                       | 塔希亚                                                                             |
| Firkraag                                                                                                                                                                                     | 费尔克拉格                                                                           |
| Ribald                                                                                                                                                                                       | 里巴尔                                                                             |
| Aerie / Imoen / Anomen / Cernd / Edwin / Haer'Dalis / Jaheira / Jan Jansen / Keldorn / Korgan / Mazzy / Minsc / Nalia / Neera / Païna / Rasaad / Viconia / Valygar / Yoshimo / Dorn / Hexaat | 爱黎／爱蒙／阿诺门／瑟恩德／艾德温／海尔达利／贾希拉／扬・詹森／凯尔登／科根／玛兹／明斯克／娜莉亚／妮拉／派娜／拉萨德／维康尼亚／瓦里格／吉野／多恩／赫克萨特 |
| Mystic Axe of Entropy                                                                                                                                                                        | 熵之秘斧                                                                            |
| Incomprehensible Map                                                                                                                                                                         | 不可解读的地图                                                                         |
| Elvish Dwarven Chain mail                                                                                                                                                                    | 精灵矮人链甲                                                                          |
| Urn of Greenbeard                                                                                                                                                                            | 绿胡子的骨灰瓮                                                                         |
| Kim's Mask / Kim's Corpse                                                                                                                                                                    | 金的面具／金的尸体                                                                       |

## 五、保留不译



* 占位符原样保留：`<CHARNAME>`、`<PRO_HESHE>`、`<PRO_HIMHER>`、`<PRO_HISHER>`、`<PRO_LADYLORD>`、`<PRO_MANWOMAN>`、`<PRO_RACE>`。

* 卓尔语（不译，保留原文）：`elg'caress`、`suliss`、`ja'lluk`、`abbil`、`Rivvin`／`rivvin`、`tan'aari`。

* 规则术语：`TAC0`、伤害骰写法 `1D8`（与游戏内原版格式一致）。

* 代码用字符串：`COPY`／`AUTO_TRA`／`APPEND ~pdialog.2da~` 等行、文件名 `lichkim`／`tanarik` 均未改动。

## 六、校验记录（9 项，全部通过）



| # | 校验项                                                   | 结果 |
| - | ----------------------------------------------------- | -- |
| 1 | 文件齐备：15 个 tra，文件名与英文侧完全一致（含 `barbe2.TRA` 的大小写）        | ✔  |
| 2 | 无 BOM（逐文件按字节检查 `EF BB BF`）                            | ✔  |
| 3 | UTF-8 严格解码无异常                                         | ✔  |
| 4 | 纯 CRLF（无裸 LF、无 `\r\r`）                                | ✔  |
| 5 | `@N` 条目总数与英文一致：2527 = 2527                            | ✔  |
| 6 | 编号集合逐文件与英文完全相同（含 `KimJ.tra` 的异常编号 `@9445` 与 `@10425`） | ✔  |
| 7 | 无重复 `@N`                                              | ✔  |
| 8 | `~` 总数逐文件与英文完全相同                                      | ✔  |
| 9 | 译文无残留英文（仅剩白名单：占位符、卓尔语、`TAC0`、`1D8`）                   | ✔  |

## 七、备注



1. `@9445`**&#x20;与&#x20;**`@10425`**&#x20;是原作者编号笔误**：`KimJ.tra` 里在 `@944` 之后写成 `@9445`、在 `@1042` 之后写成 `@10425`。为保证与 `.d` 里的引用、以及 `ADD_JOURNAL`／`REPLACE ~99999~` 的 strref 对齐，汉化文件**照原样保留这两个编号**，不改顺序、不改号。

2. `Schinese`**&#x20;目录与&#x20;**`LANGUAGE`**&#x20;的大小写**：tp2 中 `LANGUAGE ~Schinese~ ~schinese~ ~KimPirate/Schinese/Setup.tra~`，`AUTO_TRA ~KimPirate/%s~` 会按 `schinese` 去找目录。Windows／EET 下文件系统大小写不敏感，可正常工作（Linux／macOS 上原作者这一设定本身就会出问题，与本汉化无关）。

3. **English 侧未改动**：`KimPirate/English/` 下 15 个 tra 与原文件逐字节相同，未留 `.bak`（本型模组不需要）；唯一改了源码的是 `KimPirate.tp2`，已备份为 `KimPirate.tp2.bak`。

4. **安装**：把 `Schinese/` 目录随模组一起放到游戏目录，安装时语言选「Schinese」。若安装时出现 `No translation provided for @N`，说明该编号的 tra 未被 `AUTO_TRA` 取到 —— 检查 `Schinese` 目录名与 tp2 的 `~schinese~` 是否被系统区分大小写。

5. 物品描述里的 `STATISTICS:` 统一译为「属性：」，字段名统一为：属性／伤害／伤害类型／重量／速度因子／熟练类型／类型／需求／护甲等级／战斗能力／再生。