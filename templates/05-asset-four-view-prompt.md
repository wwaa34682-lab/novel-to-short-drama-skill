# 步骤5 · 资产提示词模板

> 原则：先盘点、能复用就不新建。缺什么补什么。
> 资产登记表要记三种状态：**可用 / 空壳（节点在，但没有有效图） / 作废**。步骤7 只能 @「可用」的。

## 人物四视图（一张图合成，白底）

```
Character turnaround sheet, ONE single image on pure white background, no scenery, no text, no labels.
Four views side by side, same person, same outfit, consistent proportions:
(1) front full body, (2) side full body (profile), (3) back full body, (4) front half-body bust close-up.
Subject: <性别>, <年龄段>, <面孔/族裔，例：East Asian (Chinese) face>, <脸型/五官特点>, <发型发色>.
Outfit (locked, identical in all four views): <上衣>, <内搭>, <配件/装备>, <裤>, <鞋>.
State: <干净 / 轻度战损：灰尘、旧干血渍…>.
Style: <从 STYLE-LOCK 抄：例 photoreal, live-action look, natural skin texture>, even studio lighting.
Avoid: anime, cartoon, semi-realistic 3D, ancient costume, grid of different people, extra limbs, readable text or logos.
```

中文版要点：白底、一张合成、四个视图（正面全身 / 侧面全身 / 背面全身 / 正面半身）、同一人同一套衣服、不要背景、不要文字标签。

## 场景资产
```
<地点>, <时代/城市类型>, <夜/日 + 光源设定>, <破败程度/氛围>, empty of people, 16:9, <画风>.
No readable signs, no brand names, no letters.
```

## 道具 / 怪物资产
```
<道具或生物>, <尺寸参照>, <材质/颜色>, <关键特征（剧情钉点要拍清）>, neutral dark background, <画风>.
No text on the object.
```
- 道具上如果原著有文字（符纸、招牌、纸条），资产图**不要求可读文字**，后期剪辑时叠加。带可读文字的资产不要挂进视频生成。

## 核对清单
- [ ] 性别、年龄和角色表一致（踩过的坑：年轻男性被画成女性）
- [ ] 面孔、画风、年代符合风格锁
- [ ] 四视图是**一张**合成，不是拆成好几张
- [ ] 服装和后续 Clip 写的固定服装一致
- [ ] 不合规的旧资产已经删掉或标作废，防止误用
- [ ] 登记表更新了（名称 | 类型 | 状态 | 用途）
