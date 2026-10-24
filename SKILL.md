---
name: xxd-shop-005
description: "Create XXD Shop 005 bright, tidy, lived-in beauty scene photos (明亮规整的美妆电商场景图) as finished PNGs from a white-background or real product shot, a product directory, or a product name, treating the bundled original brief as the sole aesthetic authority: the product is the brightest, clearest, most complete thing in frame with legible bottle text, high-key soft indoor daylight with no dark areas, few orderly props, a stable base like a ceramic dish or stone tray, real-camera feel like a photo taken in a very tidy home. For skincare, makeup, fragrance, hair and body care. Text-free by default. Supports multiple ratios or exact sizes and several compositions per size. Also plans a 3–6 image carousel (--set) set in different corners of the same tidy home, the last echoing the first. Use when the user invokes xxd-shop-005 or asks for 美妆场景图、小红书 PLOG、种草图、护肤品场景图、化妆品生活照、种草轮播、一组种草图."
---

# XXD Shop 005｜明亮美妆场景

用本次的美妆产品图或产品名称，生成“审美很好、收拾得很干净的人家里随手拍到”的明亮美妆场景图，交付 PNG。

每次生成前，完整读取 `references/original-prompt/zh-CN.md`。这份中文原始提示词是唯一的创作与审美权威；不总结、不翻译、不混用，也不用本文件、README、样张或其他编号替代它。

每次构建生图请求前，完整读取 `references/shop-runtime.md`，它是唯一的家族运行合同。本 Skill 不另写第二套美术指导或运行规则。

所有成品直接写进 `~/Desktop/xxd/xxd-shop-005/` 下新建的一个任务目录（或 `--out` 指定的根目录），不建子目录，不自动拼总览。

## 本编号覆盖条款

**原稿的样例任务已移除。** 原始文件末尾有一段本次任务：“左右各一种风格迥异、不同用途的日常美妆产品，比例 3:2，side by side”。那是当时的样例，不是这套风格的一部分，归档原稿已删去（见 `references/original-prompt/README.md`）。用户想要双品并排时，作为用户额外要求原话追加在末尾，例如“左右并排两件产品，各自一个场景，3:2”。这时两张图是两件不同商品的商品图，同时放进一张画布：商品块里分别写“图 1：商品图（商品 A）”“图 2：商品图（商品 B）”，各自锁定外观，不互相混合。用户只给了两张图、没说是双品还是同一商品多角度时，先问。

**本编号不问文字方式。** 原稿没有标题或排版逻辑，“按原稿生成”和“不要文字”在这里结果相同：除包装原有文字外不新增任何文字。所以默认按 `--text none` 执行，不问文字方式也不问语言；用户自己给了文案时按 `--text exact` 处理（`--text plan` 同样按 exact），并问一次语言。原稿是一张“真实相机拍摄感”的生活照，加文案时说明这会偏离拍摄感。

**瓶身文字要读得清。** 原稿要求“瓶身文字尽可能清晰”。有产品图时，标签文字、Logo 与包装图形必须与原图一致、可读、不糊、不乱码；道具、反光和阴影不能压住标签。

**适用范围：** 护肤、彩妆、香氛、洗护、身体护理、小型美容仪。家居小物也可以用，但原稿的道具语境是美妆台面与收纳；其他品类更适合 `xxd-shop-001`。

**功效不上画面。** 本编号没有文字，自然不写功效；用户追加文案时，美白、祛痘、抗老等功效词同样需要事实来源。

**套图：种草轮播（启用）。** 原稿说画面像“审美很好、收拾得很干净的人家中自然拍到的美妆照片”，一套轮播就是同一个家里的几处角落。按家族“套图”一节执行，本编号的约定：

- **默认张数：** 4。用户可以用 `--set N` 改成 3–6 张。
- **套图角色：** 每张一个承载处，从原稿列出的承载面和道具里组合：浅色陶盘、石材托盘、干净桌面、简洁收纳区域；规整收纳柜、简洁托盘、玻璃罐、镜框、折叠织物、金属置物架、花朵或书籍。每张的承载面不同，道具仍按原稿“主动克制”，只选少量。
- **继承项：** 同一个家。也就是墙面与台面的材质和色系、光的方向与高调亮度、浅色之间的明度关系。
- **构图来源：** 原稿的“居中或轻微偏心”，加上远近变化（中景交代所在的角落，近景让瓶身文字更清楚）。相邻两张在承载处或远近上不同；不为求变化而用原稿禁止的斜线、遮挡或前景虚化。
- **末张呼应首张：** 最后一张回到第 1 张的承载处，换一个远近，让轮播首尾相接。
- **文字：** 本编号默认不加字，套图也一样；用户给了每张的文案时，按 exact 逐张分配。
- **追加验收：** 一眼看得出是同一个家、同一束光；每张商品都是画面里最亮、最完整的东西；每张的承载处不同；末张与首张是同一处、不同远近。

**追加验收：** 没有大面积暗部、暗角、黑色背景或强侧光；道具少而规整，没有随机散落和前景虚化物；白色与浅色区域不发灰、不发黄；产品是画面里最明亮、最完整的东西。

**写入提示词：** 以下句子原话放进交付块的“本编号约束”；其余覆盖条款由 Agent 执行与验收，不进入提示词。

- 画面边缘和最前景不放虚化的花草、织物或任何道具；商品居中或轻微偏心，是画面里最明亮、最完整的东西。

## 参考文件

- `references/shop-runtime.md`：家族运行合同
- `references/original-prompt/zh-CN.md`：运行时使用的原始提示词
- `references/original-prompt/README.md`：译文索引、权威说明与样例任务移除记录
- `references/runtime-preferences.md`：交付偏好沿用
- `references/sample-workflow.md`：仅用于维护样张
- `scripts/configured_imagegen.py`、`scripts/shop_preferences.py`
- `scripts/clean_marks.py`：验收时放大文字区逐字核对，并抹掉品牌名旁多出来的 ®、™
