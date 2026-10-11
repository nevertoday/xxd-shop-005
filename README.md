<div align="center">

# 🦁 XXD Shop 005｜明亮美妆场景

### 收拾得很干净的家里，随手拍到的那一瓶

<strong>简体中文</strong> · <a href="README.en.md">English</a>

</div>

> 原始提示词：[简体中文原文](references/original-prompt/zh-CN.md) · [English](references/original-prompt/en.md)

## 样张

暂无样张。下文命令只是用法示例，不是视觉证据。

## 它解决什么

美妆种草图有两种常见的失败：一种是棚拍感太重，像广告不像生活；另一种是“随手拍”拍成了杂乱，桌上东西一堆，瓶子上的字被反光吃掉。

**Shop 005** 要的是中间那条线：**真实相机的生活感，但整洁得像审美很好的人家里。** 高调的室内自然光把空间照透，没有暗角和重阴影；道具少，横平竖直；产品放在陶盘、石托或干净台面上，是画面里最亮、最完整、字最清楚的东西。

## 和别的编号有什么不同

- **没有文字。** 这是一张照片，不是海报。默认不加任何标题或贴纸。
- **亮。** 原稿明确排斥大面积暗部、黑背景和强侧光，所以不适合想要高级暗调的产品，那种更适合 001 或 011。
- **适合小红书 PLOG、美妆种草和电商场景图。**

## 你需要准备

- **产品图：** 白底图或实拍图都行，瓶身文字、Logo、标签会照着保留。没有图也能按产品名生成。
- **产品用途：** 例如“晨间精华”“浴室身体乳”。场景和道具会跟着用途走。

## 使用窍门

- **小红书用 3:4，** 电商场景图 1:1。
- **想要两件产品左右并排，** 在描述里直接说“左右并排两件产品，各自一个场景，3:2”，它会作为你的额外要求加在最后。
- **标签字小的产品，** 给一张正面清楚的原图，比多角度图更重要。

## 开始使用

```bash
git clone https://github.com/nevertoday/xxd-shop-005.git
ln -s "$(pwd)/xxd-shop-005" ~/.claude/skills/xxd-shop-005
```

```text
# 一瓶精华，小红书竖图，不加文字
/xxd-shop-005 ./精华.png --product "烟酰胺精华 30ml" --use 小红书种草 --size 3:4 --text none

# 两件产品左右并排
/xxd-shop-005 ./洗发水.png ./护手霜.png --size 3:2 --text none 左右并排两件产品，各自一个场景，用途不同

# 一整个产品目录，统一做电商场景图
/xxd-shop-005 ~/Desktop/秋冬护肤/ --use 电商场景图 --size 1:1 --text none
```

常用参数：`--product` · `--use` · `--size` · `--count` · `--text none`（默认，不会问）。完整参数见[家族运行合同](references/shop-runtime.md)。

## 边界与信任

- 原始提示词逐字保存，是唯一的审美权威。原文件末尾的样例任务（左右双品、3:2）已删去，删除记录在[原始提示词目录](references/original-prompt/README.md)。
- 瓶身文字和 Logo 不改写、不乱码；画面不写功效。
- 交付 PNG 位图；每次调用都新建任务目录。

<!-- xxd-shop-tail -->
## 项目结构

```text
xxd-shop-005/
├── SKILL.md
├── README.md / README.en.md
├── LICENSE
├── agents/openai.yaml
├── assets/examples/
├── scripts/
│   ├── configured_imagegen.py
│   └── shop_preferences.py
└── references/
    ├── shop-runtime.md
    ├── runtime-preferences.md
    ├── sample-workflow.md
    └── original-prompt/
        ├── README.md
        ├── zh-CN.md
        └── en.md
```

<!-- xxd-readme-ads:start -->
## 关于 XXD

XXD 是小小东品牌名的缩写，本项目由小小东创建并维护：[@xiaoxiaodong01](https://x.com/xiaoxiaodong01)。

## 小小东多端会员 · 699 元/年

> **广告与商业信息声明：** 以下二维码、会员与付费服务链接属于小小东的广告信息。是否扫码或购买完全自愿，不影响本开源项目的访问与使用。

一次年费，同时开通三项会员权益：**知识星球 + 小小东成员提示词库 + 全部 将军总指挥 Skills 会员**。三项权益合并在同一份会员中，无需分别购买。

<!-- xxd-shop-command-system:start -->

### Skills 如何协作

| 层级 | 包含内容 | 用途 |
|---|---|---|
| **General** | `xxd-shop-all` | 识别可用的编号 Skills，按商品、用途和画面需求推荐，并组织多风格试稿与批量任务。 |
| **Soldier** | `xxd-shop-NNN` | 每个编号执行自己的原始提示词与审美，完成 General 分派的具体任务。 |

<!-- xxd-shop-command-system:end -->

### 会员权益

1. **微信一对一 AI 学习与项目答疑**
   扫描下方二维码，添加小小东微信，围绕 AI 学习、工具使用和实际项目进行一对一沟通，获得答疑与建议；代表性问题将整理为会员内容。
2. **持续更新的成员提示词库**
   [小小东成员提示词库](https://vip.xiaoxiaodong.ai/)当前约有 3.2 万条提示词，会持续整理和扩充，目标超过 10 万条。
3. **全部 将军总指挥 Skills 与使用答疑**
   一份会员覆盖全部 将军总指挥 Skills；使用过程中遇到问题，可以获得相应的使用说明与答疑。
4. **高频刚需优先处理**
   会员提出的高频、刚需提示词与 Skills 需求，会优先评估和开发。

### 如何开通

- 可在[成员网站](https://vip.xiaoxiaodong.ai/)自助开通。
- 也可以扫描下方二维码，添加小小东微信，进行一对一沟通并获得开通协助。

<p align="center"><a href="https://xiaoxiaodong.pages.dev/assets/wechat-qr.png"><img src="https://xiaoxiaodong.pages.dev/assets/wechat-qr.png" alt="联系小小东" width="280"></a></p>
<!-- xxd-readme-ads:end -->

## 许可证

本项目（包括 Skill、提示词、脚本、文档及随附样张）采用 **PolyForm Noncommercial License 1.0.0**。完整法律条文请见 [LICENSE](LICENSE)，官方页面见 <https://polyformproject.org/licenses/noncommercial/1.0.0>。

用人话说：

- 个人可以用于学习、研究、实验、测试、兴趣项目和私人娱乐；慈善机构、教育机构、公共研究/安全/卫生机构、环保组织及政府机构也可以使用。
- 在**非商业目的**下，你可以使用、复制、修改、制作衍生作品并分享；分享时必须同时提供本许可证（或上面的链接）以及作者提供的所有 `Required Notice:` 声明。
- 不允许用于商业产品或服务、收费交付、出售访问权或许可，或任何预期会带来商业应用的用途。需要商业使用时，请先向版权方另行取得书面许可。
- 本协议只授予其中明确写出的著作权许可和有限的专利许可，不授予商标、品牌名称或其他未明确授予的权利，也不能把你的许可再转授给他人。
- 如果收到书面违约通知，须在 32 天内纠正并采取实际补救措施，否则许可会立即终止；就专利侵权提出书面主张也会终止专利许可。
- 内容按“现状”提供，在法律允许的范围内不作任何担保，使用风险和可能的损失由使用者自行承担。
