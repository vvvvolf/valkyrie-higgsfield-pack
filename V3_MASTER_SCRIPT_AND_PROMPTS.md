# 《免税区女武神：蓝方块越位》十分钟出头（10:15）导演重制版剧本与 Higgsfield × Seedance 2.5 全套提示词（质感、连续性与镜头执行专业精修版）


---

# V3 专业制作统一总控版（已将 V3.1–V3.7 修订全部并入正文）

> **使用说明**：本文件为已合并所有 V3 修订的统一总控剧本与提示词。如需直接向 Higgsfield / Seedance 2.5 逐镜投喂，请配合 **[`V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md`](./V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md)**（已拆分为 **97 个 ≤120 词独立原子短镜头**，总长精确 `569.0s` + `46.0s` 字卡 = `615.0s / 10:15`）。

## V3.1 审核结论与修订目标

**结论：修改后可进入镜头测试，不建议直接整段批量生成。** 主要问题不是故事概念，而是参数口径、生成颗粒度与连续性约束：

1. 原稿将所有场景统一写成 Vision3 500T，且部分焦段/FOV 对应错误或口径未定义。
2. “3D 贴图级精修”容易让模型误以为要改变人物造型或生成真正的 3D 资产；单张 2D 图像提示词只能控制可见表面表现，不能保证生成真实 PBR 贴图、几何或 UV。
3. 26–30 秒 Master Block 中包含 4–6 个镜头、多个角色、动作和对白，不应作为一个长视频提示词一次生成。
4. 15° 激光偏斜、2mm 残余偏移、淀粉/染发剂证据、羽毛悬浮和最终付款之间，需要明确因果链。
5. Block 20 与 Card 10 都出现蓝屏收尾，容易形成重复片尾。

## V3.2 全片摄影与焦段规范（替换 V2 中所有 FOV 标注）

**统一口径：全画幅 36×24mm、对角视场角（Diagonal FOV），焦距为实际焦距；不再混用水平 FOV、垂直 FOV 与对角 FOV。** 下表为近似值，镜头呼吸、变形宽银幕附件和后期裁切会改变最终画面范围。

| 焦距 | 全画幅对角 FOV | 建议用途 |
|---:|---:|---|
| 14mm | 114° | 极端贴地/空间夸张；人物靠边会明显变形 |
| 16mm | 107° | 窄巷建立、强透视；避免脸部近距离特写 |
| 18mm | 100° | 环境广角、多人空间关系 |
| 24mm | 84° | 全景、动作空间、跟随镜头 |
| 28mm | 75° | 动作中景、人物与环境兼顾 |
| 35mm | 63° | 标准叙事、横移跟拍 |
| 40mm | 57° | 自然视角、轴线转换 |
| 50mm | 47° | 人物中近景、对白 |
| 85mm | 28° | 肖像、手部/道具细节、压缩空间 |

**全片摄影前缀（按场景替换原统一 500T 前缀）：**

```text
Cinematic live-action, 2.39:1 anamorphic composition, 180-degree shutter, natural motion cadence, restrained film grain, highlight roll-off, realistic skin and fabric response. Lens focal length is stated in millimeters; all FOV values refer to full-frame diagonal FOV before any anamorphic crop. Preserve natural perspective and avoid ultra-wide facial distortion. No artificial slow motion unless explicitly specified.
```

**胶片/色彩分场景：**
- Block 01–04 威尼斯烈日日景：以 Vision3 250D 的日光负片观感为参考；保留白石高光细节、自然肤色和硬日光阴影。
- Block 05–08 船坞正午/下午：日景仍以 250D 观感为主；红锈与克莱因蓝分离，不把蓝天染成青绿色。
- Block 09–12 黄昏死巷：转为 500T 暖逆光观感；控制橙色高光，不让肤色变橘。
- Block 13–18 地下掩体：以 500T 低照度观感为参考；黑位保留枯木、黑曜石、天鹅绒纹理，冷白顶光是唯一主光源。
- Block 19–20 次日清晨：回到 250D 日景观感；Block 20 后半再做 2D Risograph 风格转译。

> “Vision3 250D/500T”是摄影风格参考，不是生成模型可验证的胶片型号、冲洗工艺或真实 LUT。不要在提示词中承诺 100% 复刻某一胶片。

## V3.3 角色、皮肤、面料与道具质感 Prompt（替换原“3D 贴图式”措辞）

将原章节“3D 贴图式去塑料质感精修”改称 **“电影级表面材质与光照外观精修”**。以下提示词用于图像精修；不得改变身份、脸型、五官、发型轮廓、服装剪裁、配色、配饰或画面构图。

```text
[Photoreal Surface & Lighting Polish — use with the matching character reference]
Preserve the exact identity, facial proportions, expression, hairstyle silhouette, costume design, seams, accessories, pose, framing and original color palette. Do not redesign, beautify, age-shift, replace, or add objects. Improve only the visible photographic surface rendering: natural pore variation and fine vellus hair; subtle subsurface skin scattering without waxy highlights; realistic eye moisture and restrained specular reflections; individual hair strands with believable flyaways; fabric weave, seam stitching, fiber variation, weight and gravity-driven folds; physically plausible leather/paint reflections with roughness variation and controlled highlight roll-off. Keep shadow detail and natural color separation. Add fine, restrained film grain only after preserving texture detail. No beauty retouching, no airbrushed skin, no silicone/plastic sheen, no oversharpening, no fake 3D bevels, no extra jewelry, no costume changes, no background redesign.
```

**角色专属材质附加句：**
- Elena：象牙白重磅真丝，细密斜纹与重力垂坠；翠绿腰带为哑光织物；金高跟为真实金属/皮革混合反射。
- Valentina：芭比粉漆皮需有清晰环境高光、局部粗糙度变化和弯折折痕；禁止整件像塑料玩具般均匀镜面。
- Chloe：粉白格纹为厚实棉质斜纹布，格线随褶皱自然变形；鞋底橡胶有细微磨损。
- Margaux：粗花呢纤维可见但不夸张；软呢帽和相机皮革分别呈现不同粗糙度。
- Jinx：蓝色脏辫由多股纤维捻成，根部与发尾粗细有变化；弹簧靴金属件有磨损、油污与真实高光。

**道具锁定补充（@prop_klein_cube）：**
```text
The prop consists of a solid 20cm × 20cm matte Klein-blue metal plinth, a transparent protective glass canopy with visible thin edges and corner mounts, and four fine red laser beams framing an EMPTY AIR volume. The volume contains no solid cube, no blue crystal, no ice, no liquid, no glowing core and no holographic object. The base is the only opaque blue solid. Keep the glass canopy distinct from the empty air inside it. The front-right laser is the only damaged beam: first bent by 15 degrees, later corrected to a residual 2mm lateral offset.
```

## V3.4 生成执行规则：Master Block 只做导演总控，不直接整段生成

**强制执行方式：**
1. 20 个 Block 是剪辑/导演总控单元，不是单次生成单元。按原文硬切点拆成独立短镜头，每个镜头单独生成。
2. 单镜头优先 3–6 秒；复杂打斗、接触、道具交接、多人对白拆成 2–4 秒。单次只安排一个主要动作和一个主要镜头运动。
3. 每个镜头固定写明：镜头 ID、时长、角色人数/站位、首帧构图、唯一主要动作、尾帧状态、镜头运动、参考资产、光线方向、声音/台词归属。
4. 先生成角色卡和场景/道具静帧，再生成动作镜头；动作镜头引用同一角色卡、同一场景参考和前后镜头尾帧。不要每段重新描述并重新发明角色外观。
5. 复杂打斗按“预备姿势 → 单次接触 → 受力结果 → 反应/脱离”分镜；不要要求模型在同一短镜头内完成两次以上攻防。
6. 对白镜头一次只让一名角色清晰开口；其他角色嘴唇闭合。耳机对白明确标为 off-screen voice，不让画面人物做口型。
7. 先做无对白动作版本，确认动作与人物连续性后，再做对白/环境音版本；最后在剪辑中混音。
8. 每段生成后检查：角色身份、服装、人数、左右轴线、道具朝向、损伤状态、手持物、光线方向、字幕拼写。失败镜头局部重做，不重做整个 Block。

**可复制的单镜头模板：**
```text
[SHOT ID: B08-S04 | duration: 3.5s]
Reference: @char_jinx_image_v1 + @prop_klein_cube + previous shot final frame.
Continuity: same late-afternoon drydock alley, same Jinx costume, same overturned cart, same 3kg blue plinth; front-right laser already damaged.
Frame start: tight side close-up, both hands supporting the plinth, wrench visible in Jinx's right hand.
Single action: the wrench rebounds once and strikes the front-right corner of the plinth.
Camera: locked 85mm close-up, no zoom, no pan.
Frame end: one fresh metal scuff; laser sparks once and remains bent.
Lighting: warm late-afternoon rim from camera-left, no lighting change.
Audio: one metallic impact and brief electrical crackle; no dialogue, no music.
Constraints: exactly two hands, no extra fingers, no new characters, no object duplication, no slow motion.
```

## V3.5 连续性与因果修订（按以下内容替换对应镜头/台词）

### A. 激光损伤状态表（Block 08–15）
| 段落 | 道具状态 | 画面必须表达 |
|---|---|---|
| Block 08 前 | 四束激光垂直、稳定 | 完好状态 |
| Block 08 末 | 右前激光被管钳磕弯约 15° | 明确是“右前角”，其他三束不变 |
| Block 09–10 | 保持 15° 偏斜 | 角色可见污渍/划痕，不得自行复原 |
| Block 11 | 焊枪校正后仍残留 2mm 横向偏移 | 不再写“15°”；焊枪熄灭后状态锁定 |
| Block 12–14 | 保持 2mm 残余偏移 | 备份蓝袋里的道具外观不跳变 |
| Block 15–17 | 黑鸦检测到 +2.0mm | 屏幕、台词和画面统一用“2.0mm lateral offset” |
| Block 18 | 通过后红激光转冷白 | 只在认证通过后改变颜色 |

### B. 淀粉、染发剂与钴蓝粉末证据链（Block 11、15、16）
- Block 11 克洛伊将薯片袋口伸入玻璃罩时，袋内少量海盐调味粉/淀粉粉尘从袋口沾到罩内边缘；不要只写氮气进入而没有任何粉末接触。
- Block 11 金克丝剪下并碾碎蓝色脏辫补漆，留下微量钴蓝染料粉末；她的手套和底座边缘均可有极少量粉末残留。
- Block 15 黑鸦检测结果改为：`TRACE STARCH: DETECTED / BLUE DYE RESIDUE: DETECTED / LASER OFFSET: +2.0 mm`。
- Block 16 买家质询统一说：`potato-starch traces, blue dye residue, and a two-millimeter laser offset`。不要在此处突然引入前面没有出现过的“德国钴粉”作为唯一证据。
- Card 09 同步改为：`WARNING: STARCH TRACE + BLUE DYE RESIDUE + LASER OFFSET +2.0mm`。

### C. 羽毛悬浮的因果链（Block 12、15、17、18）
- Block 12：羽毛静电吸附在备份蓝袋口，作为伏笔；明确羽毛不是从蓝方块内部生成。
- Block 15：羽毛仍粘在袋口，黑鸦先检测到道具偏移与残留物；不要提前把羽毛放进透明空腔。
- Block 17：通风口微风将羽毛从袋口带起；黑鸦侧翼遮挡切轴线后，羽毛进入四束激光围出的空域，并在气流减弱时悬停。画面呈现“看似违反重力”的神迹，但不解释为真实零重力。
- Block 18：认证系统显示 `VERTICAL ACCELERATION: 0.000 g (WITHIN DISPLAY RESOLUTION)` 与 `LEVITATION EVENT: VERIFIED`。买家相信的是视觉/仪器证据与艺术叙事，不要把 `MASS DELTA` 错当作重力测量。

### D. 买家倒计时修正（Block 14–16）
- Block 14 怀表特写将 `00:15` 改为 `00:39`。
- Block 15 时长 27 秒，结束时剩余约 12 秒。
- Block 16 买家说 `Twelve seconds.` 才与画面倒计时闭环。
- 如后期实际剪辑改变段落时长，怀表数字必须按最终时间线重新校准，不要仅依赖生成模型自动保持倒计时。

### E. Block 20 与 Card 10 片尾去重
- Block 20 最后 3.5 秒不再扩散纯蓝吞屏；改为 2D 海报定格后直接切黑。
- Card 10 仍按原计划紧接 Block 20 播放，作为唯一完整的 `#002FA7` 纯蓝片尾卡，3.8 秒切黑。
- 总时长保持：Blocks 569s + Cards 46s = 615s。Card 10 不并入 Block 20 的 26 秒，也不额外延长。

### F. 角色/道具名称与状态锁
- 人物统一拼写 `Margaux`；若资产文件名为 `ref_06_margot_chase.jpg`，只视为文件命名，不改变角色名。
- `Chloé` 的左脚鞋状态：Block 02 撞击后左脚失鞋；Block 03–12 保持左脚白袜/无鞋，不能在 Block 06/07/08 自动恢复双鞋；Block 19 的换装镜头如需恢复鞋，必须给一个明确的镜头外时间跳切。
- `Jinx` 白贵宾犬全片保持同一只狗；Block 05–12 随行/被抱的状态必须按镜头明确，不得复制出第二只。
- 蓝方块始终是“蓝色实心底座 + 透明罩 + 罩内空域”，不要把玻璃罩误画成蓝色立方体。
- Block 19 三人换装是明确的次日时间跳切；Elena 象牙白西装、Valentina 克莱因蓝大衣、Chloé 粉白格纹造型从 Block 19 一直延续到 Block 20。

## V3.6 字卡、UI 与声音制作规范

- 生成模型不擅长稳定生成复杂英文 UI/新闻标题/金额。Card 01–10、全息屏、怀表数字、新闻头版标题、道具标签，优先生成干净底图，再在剪辑/合成软件中排版；不要把“文字必须完全正确”作为模型生成的唯一保障。
- 字卡字体统一使用高对比无衬线/粗衬线搭配：主标题用窄体粗字，技术 UI 用等宽字体；字卡四周留安全边距，避免 2.39:1 裁切。
- 声音分三层：现场环境底噪、动作拟音、对白/耳机声。Seedance 单次生成若出现对白串音，改为后期录制/配音；所有耳机台词均标记为 off-screen，不依赖人物口型。
- 电影颗粒最后添加；不要在每一镜都叠加过重颗粒导致不同镜头噪点尺寸不一致。

> **Duty-Free Valkyrie: Klein Blue Offside (10m15s / 615s Remastered Director's Cut · V3 Production-Ready Revision)**
> 深度融合 **Higgsfield Seedance 2.5 实战工作流（`4段视频提示词.docx`）** + **`flowtube-studio` 资产/光学/表演/武戏/调色规范**，将全片重整为 **20 个「26–30 秒多镜硬切大师序列（Master Blocks）」+ 10 张高节奏 Risograph/盖·里奇风包装字卡**，总时长精准锁定 **615 秒（10 分 15 秒）**。
> **本版新增**：① 开拍前「电影级表面材质与光照外观精修 + 视频角色卡」Prompt（及 `char_buyer` / `char_heinrich` / `char_raven` 独立裁剪资产）；② Act II `Block 06–08` 升级为真 `Combat Skill` 近身攻防；③ 全片按日景（`250D`）/黄昏与地下（`500T`）分场景光学与全画幅对角 FOV 口径；④ 配套 `97` 镜原子拆分表 `V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md`。

---

## 一、总控架构与十分钟时长配比（615s = 10:15）

| 幕次 | 时间范围 | 净片长 | 包含模块 | 核心戏剧任务 |
| :--- | :--- | :--- | :--- | :--- |
| **开场 + Act I** | `00:00 – 02:11` | `131.5s` | `Card 01–04` (`13.5s`) + `Block 01–04` (`118s`) | 圣马可破封：生蚝滑铲 `0.25s` 撞飞克洛伊 → 蓝方块泄气 → 瓦伦蒂娜顺手牵羊 → 玛格特爆闪坠坞 |
| **Act II** | `02:11 – 04:51` | `160.0s` | `Card 05–07` (`14.0s`) + `Block 05–09` (`146s`) | 红蓝船坞追逐与近身攻防：金克丝接球 → 集装箱 1v2 错峰腾空反击 → 横移长镜接伊莲娜 1v1 踢腕夺位 → 侧翻磕歪激光 15° → 死胡同互呛与电击棒通牒 |
| **Act III** | `04:51 – 07:16` | `145.5s` | `Card 08` (`5.5s`) + `Block 10–14` (`140s`) | 死胡同造假手术台：1962 香水 + 韩国海盐薯片氮气 + 柏林钴蓝染发粉 + 焊枪余 2mm → 飘落白鸽羽毛 → 降入地下五层 |
| **Act IV** | `07:16 – 09:17` | `121.0s` | `Card 09` (`8.0s`) + `Block 15–18` (`113s`) | 哥特棋盘审讯：光谱仪红警 → 伊莲娜牛津腔洛伦兹力反杀 → 黑鸦遮挡换轴线 → 白鸽羽毛微流静电悬浮 `0.000 g` 放款 8000 万欧 |
| **Epilogue** | `09:17 – 10:15` | `57.0s` | `Card 10` (`5.0s`) + `Block 19–20` (`52s`) | 船坞香槟狂欢 + 《Venice Ledger》头版误读 → 免税大道三人听耳机闭嘴行进 → 3D 坍缩 2D 丝网印定格切黑（接 Card 10 纯蓝片尾） |
| **总计** | **`00:00 – 10:15`** | **`615.0s`** | **20 Blocks (`569s`) + 10 Cards (`46s`)** | **10 分 15 秒标准十分钟出头电影感节奏** |

---

## 二、开拍前必跑：电影级表面材质与光照外观精修 + 视频角色卡规范

> 遵循教程铁律：**在锁定所有角色、面料、皮肤与道具物理质感前，不要直接拍正片。**

### 1. 主角「电影级表面材质与光照外观精修」Prompt（用于把 `assets/char_*.png` 升级为电影级皮肤与面料质感）
> 完整规范见上方 **V3.3**；不得改变人物身份、服装剪裁、配色与构图。审判庭三人图已额外拆分为 `char_buyer.png`、`char_heinrich.png`、`char_raven.png` 避免串脸。
```text
[Photoreal Surface & Lighting Polish — 投喂对应 @char_* 图片]
Preserve the exact identity, facial proportions, expression, hairstyle silhouette, costume design, seams, accessories, pose, framing and original color palette. Improve only the visible photographic surface rendering: natural pore variation and fine vellus hair; subtle subsurface skin scattering without waxy highlights; realistic eye moisture and restrained specular reflections; individual hair strands with believable flyaways; fabric weave, seam stitching, fiber variation, weight and gravity-driven folds; physically plausible leather/paint reflections with roughness variation and controlled highlight roll-off. Keep shadow detail and natural color separation, plus restrained film grain. No beauty retouching, no silicone/plastic sheen, no costume changes, no background redesign.
```

### 2. 视频角色卡生成 Prompt（先生成 4 秒 `@char_elena_video_v1` 等动态角色卡）
```text
[Video Character Card — 4s · 21:9 · Audio ON]
85mm（28° FOV）中近景静物肖像，冷浅灰无缝背景。@char_elena_refined 站在画中保持克制自然呼吸，肩部随呼吸微幅起伏，双眼自然眨眼两次（眼神聚焦镜头，绝不呆滞），下颌轻微向右偏转 5° 后回正，双唇柔和闭合静止（或念一段冷峻平稳的牛津腔试音短句：“Archive seal verified. Ten minutes remaining.”）。保留皮肤毛孔、真丝纹理与细腻胶片颗粒，无夸张表情。
```

### 3. 核心道具与四大 360° 片场锁 & DaVinci `.cube` LUT 后期配比
- **`@prop_klein_cube`**：`20cm × 20cm` 哑光 99% 吸光国际克莱因蓝（`#002FA7`）金属底座（约 3kg 重）+ 四角 `1mm` 微米猩红激光束（`#B80F1A`）。**红线禁令**：四根红激光内 **100% 完全透明空虚空（EMPTY AIR）**，绝无冰块、玻璃块或发光蓝晶体。
- **Act I (`@loc_venice_arcade_v1`)**：威尼斯白石免税拱廊，单一烈日右上方斜射；后期 **`柯达.cube` (55% 混合)**。
- **Act II (`@loc_red_drydock_v1`)**：`SECTOR 04` 红锈油罐干船坞，顶光右上方打下；后期 **`富士.cube` (40% 混合)**。
- **Act III (`@loc_red_tanks_alley_v1`)**：红锈油罐铁轨死胡同，熔金夕阳逆光；后期 **`柯达.cube` (60% 混合)**。
- **Act IV (`@loc_gothic_bunker_v1`)**：地下五层黑红白哥特棋盘祭坛，**唯一冷白正顶聚光灯（Zenith Spotlight）**（提亮暗部保留枯木/天鹅绒肌理）；后期 **`Hsjsl.cube` (50% 混合)**。
- **Epilogue (`@loc_taxfree_zone_v1`)**：现代冷灰免税大道 + 2D 丝网印坍缩；后期 **`柯达.cube` (55% 混合)**。

---

## 三、全片 10 张包装字卡规划（总计 `46.0s`）

| 卡号 | 插入位置 | 时长 | 视觉与音效设计 |
| :--- | :--- | :--- | :--- |
| **Card 01** | 开场 `00:00` | `4.5s` | 黑底正中 `#002FA7` 蓝方块 + 四角红激光：`DUTY-FREE VALKYRIE // 免税区女武神：蓝方块越位`，倒计时 `VAULT LOCK: 10:00 -> 09:56`，低音定音鼓 + 机械表滴答。 |
| **Card 02** | Block 01 后 | `3.0s` | `char_elena` 孔雀绿双色 Risograph 定格卡：`ELENA // THE VALKYRIE COURIER | 10CM GOLD STILETTO | 52 BPM`，快门咔嚓。 |
| **Card 03** | Block 02 后 | `3.0s` | `char_chloe_v2` 亮黄双色定格卡：`CHLOÉ // SEOUL SNEAKER BROKER | LEFT SOLE: €5,000,000 CRYPTO`。 |
| **Card 04** | Block 03 后 | `3.0s` | `char_valentina` 芭比粉双色定格卡：`VALENTINA // MILAN HAUTE PICKPOCKET | TAX REFUND: 100%`。 |
| **Card 05** | Block 04 后 | `5.5s` | ACT II 红警闪烁卡：`AIR PURITY: 14.0% -> 0.0% | VAULT LOCK: 06:30 | CRITICAL BREACH`，潜艇警报蜂鸣。 |
| **Card 06** | Block 05 后 | `5.0s` | 左右分屏双人定格卡：`MARGAUX (FT LEICA M3)` × `JINX (2M KLEIN BRAIDS)`。 |
| **Card 07** | Block 09 后 | `3.5s` | ACT III 黑底蓝框卡：`DEAD-END COUNTERFEIT SURGERY | VAULT LOCK: 02:00`。 |
| **Card 08** | Block 10 后 | `5.5s` | 三联原料节奏卡（`0.0s / 1.8s / 3.6s`）：`1962 TURPENTINE` + `KOREAN SEA SALT` + `BERLIN HAIR DYE`。 |
| **Card 09** | Block 15 后 | `8.0s` | 光谱仪 UI 卡：前 `2.2s` 绿波扫描，后 `5.8s` 转猩红警报 `WARNING: STARCH TRACE + BLUE DYE RESIDUE + LASER OFFSET +2.0mm`。 |
| **Card 10** | Block 20 后 | `5.0s` | `#002FA7` 纯蓝片尾卡：`€80,000,000 WIRE RELEASED | SEA-SALT CRISPS: €3.50 (NO RECEIPT)`，第 `3.8s` 硬切纯黑。 |

---

## 四、全片 20 段 Higgsfield Seedance 2.5 完整提示词（615s 总控台账）

> **统一格式**：日景（`Block 01–08, 19–20`）采用 **Vision3 250D 日景观感**，黄昏与地下（`Block 09–18`）采用 **Vision3 500T 低照度观感**，全部采用 **全画幅对角 FOV + 逐秒硬切 + 物理质感 + `无旁白无音乐` 分轨音频 + 正面约束**。单镜投喂请直接使用 [`V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md`](./V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md)。

---

### ACT I：威尼斯圣马可破封（`Block 01 – 04`，`118s`）

#### Block 01｜神明降临仰拍 & 袋内密闭蓝方块透视（`30s · 5 镜硬切` · 原 S01–S02）

```text
[风格前缀] Vision3 250D 日光负片观感，2.39:1 变形宽银幕（水平微弱蓝光斑），180 度快门真实物理速度，绝无慢动作与漂浮感。
1. 场景背景：共 20 段第 1 段，30 秒，5 个镜头干脆硬切。烈日威尼斯圣马可免税拱廊（日景），东欧女押运员伊莲娜护送《1960 年尼斯空气》穿过拱廊，远景吧台侍者与迎面走来的克洛伊构成伏笔。
2. 参考素材：@char_elena_video_v1（视频卡锁定外观与冷峻音色；重磅象牙白真丝长裙、翠绿腰带、10cm 金高跟、左耳透明耳机）；@prop_klein_cube（20cm 哑光 #002FA7 底座 + 透明玻璃罩 + 纯空透明空气 + 绿灯 SEAL INTACT）；@loc_venice_arcade_v1（白大理石柱、横幅 DUTY-FREE BIENNALE、右上方单一烈日斜射；不沿用参考图构图）。
3. 空间与首帧：第 1 帧为空旷的圣马可白石拱廊地面（14mm / 114° FOV 极低仰拍），柱影向左前方拉长；路人退至 5 米外立柱阴影下。
4. 光学与逐秒动作：
- 0.0–2.0s（镜头 1，14mm / 114° FOV 首秒勘景）：空旷大理石地面与高耸白石柱、蓝天横幅定格建立几何空间。
- 2.0–8.0s（镜头 1 延续）：@char_elena_video_v1 以干脆真实步速直接从镜头正上方迈过，手提袋随步伐以真实重力摆动，正中央硬挺哑光克莱因蓝纸袋清晰；第 6.0s 镜头迅速上仰切至其冷峻侧脸，她左手食指轻按透明耳机，下颌紧绷，双唇始终柔和闭合保持绝对静止（耳机暗语为画外音，严禁张嘴）。硬切。
- 8.0–15.0s（镜头 2，85mm / 28° FOV 袋内微距）：切入克莱因蓝纸袋内部，白色衬纸沙沙分开，正中央稳稳露出 @prop_klein_cube（#002FA7 金属底座 + 透明玻璃罩内全空透明空气，绿色 LED 闪烁“SEAL INTACT”），上方伊莲娜美甲手指收紧袋绳。硬切。
- 15.0–22.0s（镜头 3，50mm / 47° FOV 拱廊中景跟拍）：伊莲娜踏着 10cm 金高跟稳步向前，真丝裙摆随风贴腿摆动；右侧香槟吧台侍者端起放满碎冰与生蚝的银盘转身。硬切。
- 22.0–30.0s（镜头 4/5，26.0s 硬切 85mm / 28° FOV 特写）：22.0–26.0s 35mm（63° FOV）纵深镜头里远处粉发克洛伊捧着明黄鞋盒走来；26.0–30.0s 切伊莲娜冷峻近景，她眼角余光扫过前方（保持自然眨眼，眼神绝不呆滞），双唇闭合静止。
5. 物理与画质：清晰呈现大理石地面反光、真实皮肤毛孔与丝绸织纹、指节与指甲锐利清晰，无肢体融合。
6. 音频（无旁白无音乐）：[环境音] 地中海微风、远处香槟杯轻碰。[音效] 2.5–6.0s 清脆高跟敲石声；9.0s 衬纸沙沙声。[对白] 6.2–7.8s & 26.5–29.5s 仅画外近场耳机低语（画面嘴唇闭合）：“Ten minutes to vault lock. Guard the 1960 Nice air seal.” / “Not even a photon gets in.”
7. 正面约束：仅 1 名近景主角（伊莲娜）与远景模糊克洛伊、侍者；蓝方块内 100% 透明空空气，绝无冰块或晶体。
```

---

#### Block 02｜致命生蚝滑落、一字马滑铲撞鞋盒与蓝方块破封（`30s · 6 镜硬切` · 原 S03–S06_v2）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实物理速度，碰撞瞬间带短暂定向动态模糊，随后定格在清晰接触姿态，严禁任何慢动作！
1. 场景背景：第 2 段，30 秒，圣马可免税拱廊（日景），6 个镜头硬切。生蚝滑落，伊莲娜 10cm 细高跟 0.25 秒踩碎生蚝失控一字马滑铲，把克洛伊连人带黄鞋盒撞飞，飞鞋踢裂蓝方块玻璃罩泄出一缕 1960 白雾。
2. 参考素材：@char_elena_video_v1（象牙白真丝长裙、翠绿腰带、10cm 金高跟）；@char_chloe_image_v2（粉短发、荧光黄墨镜、黄短针织+粉白格纹工装夹克长裤、白色厚底老爹鞋、怀抱明黄 LOOP LAB 鞋盒）；@prop_klein_cube；@loc_venice_arcade_v1。
3. 空间与轴线：单一右上方烈日。伊莲娜自左向右横向滑铲（1v1 错峰撞击），克洛伊从右侧迎面走来，4 米内无路人。
4. 光学与逐秒动作：
- 0.0–4.5s（镜头 1，50mm / 47° FOV 甩镜接地面）：香槟吧台侍者银盘倾斜，带壳生蚝从碎冰滑落，啪嗒湿滑掉在抛光白大理石地面正中。硬切。
- 4.5–9.0s（镜头 2，85mm / 28° FOV 贴地微距）：金色 10cm 细高跟垂直落下，在 0.25 秒内干脆踩碎生蚝壳与蚝肉，汁水与碎壳飞溅，鞋跟瞬间丧失摩擦力向右侧猛烈打滑飞出画面。硬切。
- 9.0–15.0s（镜头 3，35mm / 63° FOV 横向低机位，Combat Skill）：@char_elena_video_v1 上半身如大理石雕像挺直冷静、乌黑长发甩开，贴地高速一字马向前滑行，前脚在 0.25 秒无蓄力直线冲击中狠狠铲进 @char_chloe_image_v2 小腿胫骨（接触处布料产生真实受力形变），克洛伊重心失衡向后仰倒。硬切。
- 15.0–20.5s（镜头 4，85mm / 28° FOV Match-cut 受力特写）：克洛伊向后倒飞，左脚白色厚底老爹鞋鞋底贴近镜头前猛然砸过，明黄“LOOP LAB”鞋盒炸飞；镜头边缘切回伊莲娜单膝压稳滑停，眼神聚焦空中坠物（自然眨眼），冷静开口（仅伊莲娜动嘴）：“Minor maritime turbulence.”。硬切。
- 20.5–25.5s（镜头 5，35mm / 63° FOV 仰望深蓝天空）：撕裂蓝纸袋将约 3kg 重的 @prop_klein_cube 抛至半空正中央，一只飞舞的白老爹鞋在空中磕开玻璃罩金属卡扣，罩内纯空气“嘶”地冒出一缕极细白色气压雾气后消散（内部依旧空空如也，绝无冰块）。硬切。
- 25.5–30.0s（镜头 6，50mm / 47° FOV 追随）：蓝方块沿抛物线越过拱廊边缘向街角精品店坠落，克洛伊摔坐在地摸着光着的左脚袜子呆滞抬头。
5. 画质与音频（无旁白无音乐）：皮肤毛孔与冲击动态模糊自然。[音效] 3.8s 生蚝拍地；6.2s 脆壳“咔嚓”+鞋底猛滑“SKRRRRT”；12.5s 0.25s 沉重撞击闷响；16.0s 鞋盒炸飞碰撞；23.0s 卡扣弹开+泄气“PSSSHHH！”。[对白] 18.2–19.8s Elena: {Minor maritime turbulence.}（克洛伊张嘴喘气无台词）。
6. 正面约束：碰撞圈内仅伊莲娜与克洛伊 2 人；180 度快门真实重力加速度；蓝方块内无冰块无水晶。
```

---

#### Block 03｜芭比粉礼盒雨顺手牵羊 & 女武神起身通联（`28s · 4 镜硬切` · 原 S07–S08）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实物理速度。
1. 场景背景：第 3 段，28 秒，圣马可拱廊精品店出口与大理石地面（日景），4 个镜头硬切。瓦伦蒂娜在礼盒雨中接住蓝方块，伊莲娜起身弹壳，克洛伊单脚蹦跳追喊五百万加密币，伊莲娜耳机下令五分钟追回。
2. 参考素材：@char_valentina_image_v1（齐下巴黑波波头、高光泽芭比粉漆皮风衣、粉猫眼墨镜、敞开的粉鳄鱼皮包）；@char_elena_video_v1；@char_chloe_image_v2（粉白格纹、左脚仅穿白袜、右手高举失落的左脚白球鞋）；@prop_klein_cube；@loc_venice_arcade_v1。
3. 光学与逐秒动作：
- 0.0–6.0s（镜头 1，18mm / 100° FOV 高饱和广角）：精品店门口落下粉白礼盒雨，@char_valentina_image_v1 踩高跟走出，天上坠落的 @prop_klein_cube 不偏不倚“咚”地砸进她胸前敞开的粉鳄鱼皮包（包身受 3kg 重力下沉变形）。硬切。
- 6.0–12.0s（镜头 2，50mm / 47° FOV 瓦伦蒂娜近景）：瓦伦蒂娜单指推下粉墨镜半寸，窥见包里克莱因蓝底座，嘴角冷笑勾起，“啪”地扣上包扣，开口道：“God truly adores tax evaders.”，随即转身快步走向窄巷。硬切。
- 12.0–20.5s（镜头 3，35mm / 63° FOV 低机位跟拍）：@char_elena_video_v1 单手撑地优雅一跃起身，抬左脚从 10cm 金高跟尖弹掉一片碎蚝壳；后方 @char_chloe_image_v2 单脚蹦跳冲上来，挥舞失落的左脚老爹鞋大喊：“My left sneaker! Five million in crypto is in that sole!”（伊莲娜背对镜头保持闭嘴）。硬切。
- 20.5–28.0s（镜头 4，85mm / 28° FOV 伊莲娜侧脸推近）：伊莲娜无视克洛伊，左手食指按住左耳透明耳机，眼神锁定远去粉色身影（自然眨眼，绝不呆滞），双唇柔和闭合静止（绝不张嘴），画外音耳机传出冷声：“Heinrich, give me five minutes.”。
4. 物理与画质：瓦伦蒂娜漆皮风衣必须呈现高光泽折痕反光与真实皮肤毛孔；包口扣合后严丝合缝。
5. 音频（无旁白无音乐）：[音效] 4.2s 重物落包闷响；10.5s 金属包扣“啪嗒”；14.0s 指甲弹蚝壳轻响。[对白] 8.5–10.3s Valentina；15.8–19.8s Chloé；24.0–26.8s Elena（仅画外耳机人声，画面嘴唇闭合不动）。
6. 正面约束：严格遵守单人开口与闭嘴铁律；漆皮反光清晰。
```

---

#### Block 04｜窄巷三方起跑、记者逆流举镜与高架桥坠坞（`30s · 5 镜硬切` · 原 S09–S11）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，35mm 胶片颗粒，180 度快门真实速度。
1. 场景背景：第 4 段，30 秒，威尼斯石灰岩窄巷至俯瞰干船坞高架桥（日景），5 个镜头硬切。伊莲娜与克洛伊追击瓦伦蒂娜，玛格特逆流举徕卡 M3 贴脸爆闪，瓦伦蒂娜受惊脱手，蓝方块坠向红蓝干船坞。
2. 参考素材：@char_valentina_image_v1；@char_elena_video_v1；@char_chloe_image_v2；@char_margaux_image_v1（棕色软呢帽、格纹粗花呢西装、银黑徕卡 M3 配圆形闪光灯、鲑鱼粉《THE VENICE LEDGER》）；@prop_klein_cube。
3. 光学与逐秒动作：
- 0.0–6.0s（镜头 1，85mm / 28° FOV 长焦压缩窄巷）：瓦伦蒂娜抱粉包疾走；伊莲娜穿象牙白长裙大步高速逼近，克洛伊单脚跨过露天咖啡椅紧追。硬切。
- 6.0–13.0s（镜头 2，35mm / 63° FOV 倾斜 12° 逆流）：阴影金融街口，@char_margaux_image_v1 顶着狂风逆西装人群大步走来，风将《THE VENICE LEDGER》大报和白鸽吹满半空；玛格特发现粉色风衣，双手举起徕卡 M3 锁定对焦。硬切。
- 13.0–18.5s（镜头 3，50mm / 47° FOV 贴脸强闪冲击）：高架桥铁栏旁，玛格特贴近瓦伦蒂娜半米按下圆形闪光灯——刺眼白光爆闪（不超过 0.3s）直击粉墨镜，白鸽惊飞掠过镜头。硬切。
- 18.5–24.0s（镜头 4，50mm / 47° FOV 失手瞬间）：瓦伦蒂娜受惊后仰撞在铁栏杆上，惊呼：“Che cazzo—!”（仅她动嘴），粉鳄鱼皮包扣震开，约 3kg 重 @prop_klein_cube 翻出包口越过栏杆。硬切。
- 24.0–30.0s（镜头 5，24mm / 84° FOV 高架桥俯冲追踪）：镜头随蓝方块从铁栏垂直下坠，下方红锈油罐与纯蓝天空交界的“SECTOR 04”干船坞全景急速放大，伊莲娜冲至栏杆边俯视，眼神冷峻自然眨眼。
4. 画质与音频（无旁白无音乐）：粗花呢纤维与漆皮反光清晰。[环境音] 狂风、报纸猎猎声、白鸽振翅。[音效] 15.2s 徕卡快门“咔嚓”+闪光灯电容啸叫“PING！”；21.5s 包扣崩开。[对白] 19.2–20.8s Valentina: {Che cazzo—!}。
5. 正面约束：4 位具名女性身份特征不串台；下方干船坞出现红色油罐与蓝天。
```

---

### ACT II：SECTOR 04 红蓝干船坞追逐与近身攻防（`Block 05 – 09`，`146s`）

#### Block 05｜红蓝撞色废土接球 & 购物车狂飙 POV（`30s · 4 镜硬切` · 原 S12–S13）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实物理速度，无慢动作。
1. 场景背景：第 5 段，30 秒，SECTOR 04 红锈油罐干船坞（烈日正午），4 个镜头硬切。金克丝推着生锈购物车横移接住天降蓝方块，随后以购物车颠簸第一视角冲入红集装箱迷宫。
2. 参考素材：@char_jinx_image_v1（黄铜护目镜、2 米长 #002FA7 克莱因蓝脏辫、废土红黑短裙、气动弹簧高跷靴、蓬松白贵宾犬）；@prop_klein_cube；@loc_red_drydock_v1（巨型红锈油罐“SECTOR 04 - RESTRICTED”、纯正蓝天、顶光右上方打下）。
3. 光学与逐秒动作：
- 0.0–2.0s（镜头 1，35mm / 63° FOV 首秒勘景）：巨大红锈油罐“SECTOR 04”与纯蓝天幕建立红蓝撞色空间，右侧无行人。
- 2.0–12.0s（镜头 1 延续，高速自左向右横移）：@char_jinx_image_v1 穿机械弹簧靴大步狂奔推购物车，白贵宾犬紧跟奔跑；第 6.0s 天降 @prop_klein_cube 砸进车筐正中纸箱堆（纸箱产生真实凹陷形变），金克丝不减速兴奋大喊（仅她开口）：“Pure ultramarine! Straight into my Biennale piece!”。硬切。
- 12.0–21.0s（镜头 2，24mm / 84° FOV 购物车扶手 POV）：颠簸强烈的车筐视角，正中央哑光蓝方块在油腻化油器和瘪易拉罐间真实弹跳，金克丝戴露指手套的右手伸过来拍了拍蓝方块底座。硬切。
- 21.0–30.0s（镜头 3/4，25.5s 硬切 50mm / 47° FOV 弯道侧拍）：购物车猛打方向冲进红集装箱迷宫巷道，铁轮摩擦水泥地冒出火花，白贵宾犬紧贴车侧拐弯。
4. 画质与音频（无旁白无音乐）：脏辫纤维与铁锈肌理清晰。[音效] 6.0s 重金属块砸进纸箱“DUANG！”；12–30s 铁车轮轰隆震动、易拉罐碰撞、白贵宾犬吠叫。[对白] 8.2–11.5s Jinx。
5. 正面约束：严格 1 名女性（金克丝）+ 1 只白贵宾犬全程同框；墙面文字清晰为“SECTOR 04”。
```

---

#### Block 06｜天桥跃下真丝战损 & 集装箱 1v2 错峰腾空反击（`28s · 5 镜硬切` · 原 S14–S15 升级 `Combat Skill`）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实物理打击，带短暂定向动态模糊与清晰接触姿态，无慢动作。
1. 场景背景：第 6 段，28 秒，干船坞铁楼梯与红集装箱窄巷（日景），5 个镜头硬切。伊莲娜跃下撕裂真丝长裙骑上滑板车；瓦伦蒂娜与单脚克洛伊堵住红巷前口，金克丝借集装箱墙面蹬跳腾空，用管钳 0.25 秒横扫逼退瓦伦蒂娜，同时视线转靶撞飞克洛伊手中空鞋盒冲出包围。
2. 参考素材：@char_elena_video_v1；@char_valentina_image_v1；@char_chloe_image_v2；@char_jinx_image_v1（+ 管钳 + 购物车 + 白贵宾犬）；@loc_red_drydock_v1。
3. 光学与逐秒动作（Combat Skill 拆解一对二为连续 1v1 错峰交手）：
- 0.0–6.5s（镜头 1，24mm / 84° FOV 摇臂俯冲）：@char_elena_video_v1 单手撑过高架桥栏杆干脆跃下地面，象牙白真丝裙摆被铁钩勾住，“嘶啦”撕成利落高开衩，她单脚踩上快递电动滑板车拧满油门冲入红巷。硬切。
- 6.5–12.0s（镜头 2，28mm / 75° FOV 铁楼梯包抄）：瓦伦蒂娜踏高跟哐当冲下铁梯，克洛伊单脚踩白球鞋顺铁扶手滑冲而下，大喊：“Touch that blue brick and you buy my whole inventory!”，两人一左一右堵住前方红集装箱巷口。硬切。
- 12.0–17.5s（镜头 3，50mm / 47° FOV 横向交手 1v1）：金克丝急刹停稳半拍（静止蓄势），随即左脚弹簧靴喷汽蹬上右侧红集装箱壁腾空斜飞，右手钢丝管钳在 0.25 秒内无前摇直线横扫掠过瓦伦蒂娜鼻尖两寸——逼得瓦伦蒂娜急仰头躲避，漆皮风衣衣领被气浪带偏。硬切。
- 17.5–22.5s（镜头 4，85mm / 28° FOV Match-cut 眼神转靶与撞击）：金克丝在半空脚尖未落地前视线已提前死锁左侧扑来的克洛伊胸口（眼神专注自然眨眼），落地瞬间反手推着购物车铁框 0.25 秒直线撞飞克洛伊怀里的空黄鞋盒，鞋盒受重击变形飞散。硬切。
- 22.5–28.0s（镜头 5，35mm / 63° FOV 突围）：金克丝顺势推车带白贵宾犬冲进纵深红巷，留下气急败坏爬起的瓦伦蒂娜与克洛伊。
4. 画质与音频（无旁白无音乐）：接触形变与汗珠/尘土飞扬清晰，零肢体融合。[音效] 4.5s 撕丝绸“RRRIP！”；5.8s 电机啸叫；15.2s 管钳破空“WHOOSH！”；19.5s 铁框撞飞纸盒闷响。[对白] 8.5–11.8s Chloé（其余人动作间保持闭嘴咬牙）。
5. 正面约束：1v1 错峰交手同一瞬间只有 1 名对手触及金克丝；伊莲娜在 Act II–IV 期间保持高开衩战损白丝裙（直至 Block 19 次日清晨换装）。
```

---

#### Block 07｜红蓝迷宫横移长镜、Whip-pan 接伊莲娜 1v1 踢腕夺位（`30s · 4 镜硬切` · 原 S16_v2–S17 升级 `Combat Skill`）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实速度，Whip-pan 藏接缝。
1. 场景背景：第 7 段，30 秒，红锈集装箱交错长廊（日景），4 个镜头硬切。14 秒四方错峰横移长镜头，甩镜（Whip-pan）衔接金克丝弹簧靴跃黑机油坑磕歪车轮，伊莲娜滑板车贴身截击，10cm 金高跟 0.25 秒精准点踢金克丝持钳手腕。
2. 参考素材：@char_jinx_image_v1（+ 管钳 + 白贵宾犬）；@char_elena_video_v1（高开衩裙 + 滑板车）；@char_valentina_image_v1；@char_chloe_image_v2；@loc_red_drydock_v1。
3. 光学与逐秒动作：
- 0.0–14.0s（镜头 1，35mm / 63° FOV 刚性轨道横向平推长镜，自左向右穿过三排红集装箱断面）：
  - 0.0–4.5s：金克丝弹簧靴弹跳推车狂奔，白贵宾犬紧跟；
  - 4.5–9.0s：隔两秒空档，伊莲娜端庄笔直踩滑板车静音高速滑过；
  - 9.0–14.0s：瓦伦蒂娜与单脚克洛伊狼狈狂奔紧追，头顶惊起白鸽。第 13.6s 镜头猛向右甩产生 Whip-pan 动态模糊。硬切。
- 14.0–20.5s（镜头 2，35mm / 63° FOV 接 Whip-pan 落地）：金克丝弹簧靴双筒喷出白色蒸汽跃过一大滩黑机油，落地时购物车右前铁轮“哐当”磕歪变形。硬切。
- 20.5–25.5s（镜头 3，50mm / 47° FOV 1v1 近身交锋，Combat Skill）：伊莲娜滑板车贴地急停挡在侧面，金克丝反手举管钳直线劈向车把；伊莲娜眼神先锁管钳再锁手腕，在 0.25 秒内抬右腿 10cm 金高跟鞋尖精准侧踢金克丝手腕（绝对静止对峙 → 0.25s 直线出脚 → 瞬间收腿回防稳立）。硬切。
- 25.5–30.0s（镜头 4，85mm / 28° FOV 受力插入特写 Match-cut）：金高跟鞋尖压入露指手套腕部产生真实皮肉与布料凹陷，汗珠微溅，管钳险些脱手，金克丝咬牙后撤半步推歪车狂逃。
4. 画质与音频（无旁白无音乐）：手部指节与高跟鞋金属质感锐利。[音效] 0–14s 四方节奏脚步与电机声；17.5s 蒸汽“PSSSH”+ 歪轮撞地；23.0s 0.25s 干脆踢腕闷响“THWACK！”。[对白] 无对白。
5. 正面约束：14s 横移长镜 4 人错峰经过绝不重影；近身交锋仅伊莲娜与金克丝 2 人，零慢动作。
```

---

#### Block 08｜高处狗仔连拍、滑板车截停与管钳磕歪激光 15°（`28s · 5 镜硬切` · 原 S18–S21）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实物理碰撞，无慢动作。
1. 场景背景：第 8 段，28 秒，干船坞高架猫道与铁轨窄巷（下午斜阳），5 个镜头硬切。玛格特猫道连拍低语；伊莲娜滑板车甩尾踢木托盘截停，购物车侧翻，金克丝扑救蓝方块时管钳反作用力 0.25 秒磕歪右前红激光 15 度。
2. 参考素材：@char_margaux_image_v1；@char_elena_video_v1；@char_jinx_image_v1；@prop_klein_cube；@loc_red_drydock_v1。
3. 光学与逐秒动作：
- 0.0–6.5s（镜头 1，85mm / 28° FOV 猫道望远偷拍）：玛格特趴在锈栏杆上拨动徕卡 M3 连拍下方交锋，凑近录音笔低语：“Vespera fixer chasing a squatters' cart... Pulitzer material.”。硬切。
- 6.5–12.5s（镜头 2，35mm / 63° FOV 贴地跟拍）：红巷中伊莲娜滑板车甩尾超越，金高跟侧踢一块“FRAGILE”木托盘横挡去路；金克丝歪斜的车轮一头卡死地面嵌入铁轨。硬切。
- 12.5–18.5s（镜头 3，50mm / 47° FOV 真实速度侧翻）：生锈购物车猛烈侧翻，废铁齿轮四散；金克丝扑上前在离地十厘米处双手死死接住约 3kg 重 @prop_klein_cube（手臂肌肉因承重紧绷）。硬切。
- 18.5–22.0s（镜头 4，85mm / 28° FOV 碰撞插入特写 Match-cut）：金克丝右腕一抖，重型钢丝管钳因惯性在 0.25 秒内“当！”地狠狠磕在蓝方块底座右前角，留下黑油污与细微金属擦痕。硬切。
- 22.0–28.0s（镜头 5，85mm / 28° FOV 极近微距）：底座躺在翻倒车网上，四角微米红激光激活框出全透明空虚空——唯独右前角红激光“滋啦”闪火花，肉眼可见向右歪斜 15 度。
4. 画质与音频（无旁白无音乐）：金属油污与火花高光真实。[音效] 1.5s 徕卡连拍；9.5s 刹车+木板重击；14.0s 翻车巨响；19.5s 管钳磕铁“DING！”；24.0s 短路电火花“BZZZT！”。[对白] 3.2–6.2s Margaux。
5. 正面约束：蓝方块内全透明空空气（无冰块无水晶）；右前红激光歪斜 15°；无慢动作。
```

---

#### Block 09｜死胡同三角合围、抢拍互呛与电击棒三分钟通牒（`30s · 6 镜硬切` · 原 S22_v2–S25）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门真实节奏。
1. 场景背景：第 9 段，30 秒，金色黄昏红锈储油罐死胡同（@loc_red_tanks_alley_v1），6 个镜头硬切。三女死胡同互呛（Acting Skill 提前抢反应 + 手不离物），伊莲娜拔电击棒清场，拍黑卡下达三分钟二十万欧通牒。
2. 参考素材：@char_elena_video_v1（战损高开衩白丝裙、翠绿腰带、黑电击棒、黑卡）；@char_jinx_image_v1（2 米蓝脏辫、护目镜、管钳、白贵宾犬）；@char_valentina_image_v1（高光芭比粉漆皮风衣、粉墨镜）；@char_chloe_image_v2（粉白格纹、左脚光着、手举单只白球鞋）；@prop_klein_cube（右前激光歪 15° 沾油污）；@loc_red_tanks_alley_v1。
3. 光学与逐秒动作（全员手不离物）：
- 0.0–5.0s（镜头 1，16mm / 107° FOV 倾斜 10° 广角）：夕阳逆光拉长阴影，金克丝护底座举管钳、白贵宾犬低吼；左右瓦伦蒂娜与克洛伊逼近；4.0s 伊莲娜步入前景封死出口。硬切。
- 5.0–14.5s（镜头 2，50mm / 47° FOV 快速甩镜三连拍，提前 0.3s 抢反应）：
  - 5.0–8.0s：金克丝管钳敲铁框定音怒吼：“Back off! Readymade art—touch it and I sue!”；
  - 8.0–11.2s：甩镜至瓦伦蒂娜（提前 0.3s 冷笑），单指勾下粉墨镜兼弹袖灰：“I stole it fair and square, little goblin!”；
  - 11.2–14.5s：甩镜至克洛伊，单只白球鞋怼到镜头前十厘米大喊：“You dented my five-million-euro sole!”。硬切。
- 14.5–18.5s（镜头 3，50mm / 47° FOV 伊莲娜近景）：画外三人吵闹，伊莲娜闭眼半秒，抽出黑电击棒按下开关——蓝弧“CRACK-ZAP！”爆响切入绝对死寂，她低眼瞥表。硬切。
- 18.5–21.5s（镜头 4，50mm / 47° FOV 三人定格反应）：三人瞬间僵住噤声（举钳/摸镜/举鞋），白贵宾犬垂耳闭嘴，眼神惊惧投向伊莲娜。硬切。
- 21.5–30.0s（镜头 5/6，26.5s 硬切 50mm 俯拍）：85mm（28° FOV）伊莲娜紧特写眼神从左扫右，电击棒指向歪斜激光，左手抽出黑卡冷声道：“That leaked air belongs to Russian oligarchs. Fake 1960 Nice harbor in three minutes, or mercenaries sink us all. Two hundred grand each—work.”；26.5s 黑卡“SNAP！”拍上铁网，四人双手伸向车筐。
4. 画质与音频（无旁白无音乐）：皮肤毛孔、夕阳金边发丝、漆皮高光清晰。[音效] 5.4s 敲铁框；16.2s 电弧“CRACK-ZAP”切断吵闹；27.2s 黑卡拍网“SNAP！”。[对白] 按时段独立发声，非说话者闭嘴。
5. 正面约束：精确 4 名女性 + 1 只白贵宾犬；右前红激光歪斜 15°。
```

---

### ACT III：死胡同造假手术台与潜入地下（`Block 10 – 14`，`140s`）

#### Block 10｜外科手术台总调度 & 1962 绝版香水半下定调（`28s · 4 镜硬切` · 原 S26_v2–S27）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门，暖金逆光。
1. 场景背景：第 10 段，28 秒，金色黄昏死胡同（@loc_red_tanks_alley_v1），4 个镜头硬切。四女变身急诊外科医生围拢蓝方块，伊莲娜下达配方，瓦伦蒂娜用偷来的 1962 娇兰古龙水精密喷入半下。
2. 参考素材：@char_elena_video_v1；@char_valentina_image_v1；@char_chloe_image_v2；@char_jinx_image_v1；@prop_klein_cube；@loc_red_tanks_alley_v1（旁有 GENEVA FREEPORT - LOT #00 木箱）。
3. 光学与逐秒动作：
- 0.0–2.0s（镜头 1，35mm / 63° FOV 俯拍建立）：四人同时如外科医生般俯身围拢翻倒车上的蓝方块。
- 2.0–13.5s（镜头 1 延续，倾斜中景）：伊莲娜轻敲腕表发号施令：“Nice 1960 air is 2% sea mist, trace turpentine, and old-money arrogance. Improvise.”；另三人闭嘴翻找背包口袋。硬切。
- 13.5–21.5s（镜头 2，85mm / 28° FOV 暖金微距）：瓦伦蒂娜涂粉甲的手指掏出“1962 EAU DE NICE”古典玻璃香水瓶，拧盖后对着蓝方块微裂玻璃缝隙极度克制地轻按半下喷头，一缕细腻金雾渗入透明罩内。硬切。
- 21.5–28.0s（镜头 3/4，24.5s 切双人近景 50mm / 47° FOV）：瓦伦蒂娜欲补喷，伊莲娜两指“啪”地按住她手腕阻止：“Half a spritz. It's an art gallery, not a Milanese brothel.”。
4. 画质与音频（无旁白无音乐）：手指纹理、玻璃瓶反光与香水微雾清晰。[音效] 15.0s 拧瓶盖；18.5s 轻短喷雾“PSS”；22.5s 拦腕轻碰。[对白] 仅伊莲娜两处发声，其余人闭嘴专注。
5. 正面约束：严格 4 名女性；蓝方块内保持透明虚空（无冰块）；全员手不离物。
```

---

#### Block 11｜海盐薯片挤氮气、蓝染发粉补漆与微焊余 2mm（`30s · 5 镜硬切` · 原 S28_v2–S30）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门真实质感。
1. 场景背景：第 11 段，30 秒，黄昏死胡同手术台（@loc_red_tanks_alley_v1），5 个镜头硬切。克洛伊挤入韩国海盐薯片氮气，金克丝剪蓝脏辫碾粉遮油污并开启微焊枪校准红激光，焊枪却在激光还差 2 毫米时没气熄火。
2. 参考素材：@char_chloe_image_v2（持揉皱“SEA SALT CRISPS”银箔薯片袋）；@char_jinx_image_v1（拉下黄铜护目镜、握剪线钳与微焊枪）；@char_elena_video_v1；@prop_klein_cube。
3. 光学与逐秒动作：
- 0.0–9.5s（镜头 1，50mm / 47° FOV 克洛伊近景）：克洛伊抖动银箔薯片袋（袋内微量海盐调味粉与淀粉微尘随气流沾到玻璃罩内缘），将袋口塞进微缝挤压注入氮气，“咔哒”锁死卡扣，得意道：“Artisanal sea-salt nitrogen. Zero trans fat.”。硬切。
- 9.5–17.5s（镜头 2，85mm / 28° FOV 极近微距）：金克丝用钢丝钳剪下一小撮刚染的克莱因蓝脏辫，在戴手套的掌心碾成蓝粉，细细涂抹盖住底座黑油污（手套与底座边缘留有极微量蓝染料粉末残留），哑光 #002FA7 表面恢复近似原色，她炫耀道：“Berlin industrial cobalt-blue dye No. 4. Identical hex code.”。硬切。
- 17.5–25.0s（镜头 3/4，21.5s 切 85mm / 28° FOV 激光特写）：金克丝拉下护目镜点燃微焊枪抵近底座右前角，橙色焊花四溅（21.5s 切激光特写），原本歪 15° 的细红激光慢慢被掰回垂直。硬切。
- 25.0–30.0s（镜头 5，50mm / 47° FOV 熄火瞬间）：焊枪“噗”一声断气熄灭，激光停在**越位偏斜 2 毫米**处不动，金克丝拉起护目镜惊呼：“Torch is out! Still two millimeters off!”。
4. 画质与音频（无旁白无音乐）：铝箔褶皱、脏辫粉末与焊花质感锐利。[音效] 4.5s 铝箔挤压+7.5s 卡扣锁死；10.5s 剪发“咔嚓”；18.5–24.5s 焊枪喷火与火花；25.2s 断气“噗哧”。[对白] 5.0–8.8s Chloé；13.5–17.0s Jinx；26.5–29.5s Jinx。
5. 正面约束：蓝方块内全透明空空气；25s 后焊枪完全熄灭；激光保留微小 2mm 偏斜。
```

---

#### Block 12｜猫道白鸽羽毛伏笔、甩黑卡进门与货梯三人目送（`28s · 4 镜硬切` · 原 S31–S33_v2）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门真实速度。
1. 场景背景：第 12 段，28 秒，死胡同猫道至“FREEPORT ACCESS”货梯口（黄昏），4 个镜头硬切。玛格特蹭落 6cm 白鸽羽毛静电粘在伊莲娜备份蓝袋口；伊莲娜甩黑卡步入货梯，铁栅门合拢隔开目送的三人与白贵宾犬。
2. 参考素材：@char_margaux_image_v1；@char_elena_video_v1（拎备份克莱因蓝纸袋）；@char_valentina_image_v1；@char_chloe_image_v2；@char_jinx_image_v1（抱白贵宾犬）；@prop_klein_cube。
3. 光学与逐秒动作：
- 0.0–8.5s（镜头 1，85mm / 28° FOV 仰拍猫道切地面）：猫道上玛格特软呢帽檐蹭到一只白鸽，一根 6cm 纯白羽毛飘落，悄无声息静电吸附在地面伊莲娜脚边备份蓝纸袋袋口边缘。硬切。
- 8.5–18.5s（镜头 2，50mm / 47° FOV 铁门前中景）：伊莲娜将蓝方块放入贴着羽毛的蓝袋，耳机红灯闪烁、腕表“01:15”，她把黑卡抛给瓦伦蒂娜：“PIN is 1960. Split it evenly—don't buy crypto.”，拉开通往“FREEPORT ACCESS”的铁门。硬切。
- 18.5–24.5s（镜头 3，35mm / 63° FOV 货梯内部向外 POV）：伊莲娜背对镜头整理战损白丝裙；透过缓缓合拢的重型铁栅门，瓦伦蒂娜、克洛伊、抱白贵宾犬的金克丝并肩站在夕阳死胡同沉默目送。硬切。
- 24.5–28.0s（镜头 4，50mm 门合切黑）：重型铁门“咣当”锁死，货梯内冷白微光亮起。
4. 画质与音频（无旁白无音乐）：铁网锈迹与羽毛绒毛细节清晰。[音效] 1.5s 徕卡轻响+鸽子咕咕；15.0s 黑卡拍掌心；20–25s 铁栅门滑轨声与第 25.5s 钢门闭合“KA-CLANG！”。[对白] 12.5–16.8s Elena。
5. 正面约束：羽毛清晰粘在蓝袋口；镜头 3 铁门外严格 3 女 + 1 白贵宾犬。
```

---

#### Block 13｜极速下坠电梯仪容整理 & 踏入黑红激光核掩体（`28s · 4 镜硬切` · 原 S34–S35）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，高反差冷暖碰撞，180 度快门。
1. 场景背景：第 13 段，28 秒，地下混凝土货梯井至地下五层防爆走廊，4 个镜头硬切。电梯疾坠至地下五层，伊莲娜在频闪灯下纹丝不动理衣整袋，防爆门滑开，10cm 金高跟踏入黑红激光走廊。
2. 参考素材：@char_elena_video_v1（战损高开衩白丝裙、翠绿腰带、10cm 金高跟、带白羽的备份蓝袋）；@loc_gothic_bunker_v1（黑曜石地面 + 水平猩红激光）。
3. 光学与逐秒动作：
- 0.0–12.0s（镜头 1，24mm / 84° FOV 电梯井俯拍）：层显飞快跳变“-1, -2, -3, -4, -5”；闪烁冷白荧光灯下伊莲娜纹丝不动，双手从容抚平黑发与蓝袋折痕（袋口白羽微微轻颤）。硬切。
- 12.0–16.5s（镜头 2，50mm / 47° FOV 电梯门平视）：电子屏定格“LEVEL -5 VAULT”，液压制动闷响；一米厚防爆门向两侧解压滑开露出漆黑走廊。硬切。
- 16.5–23.0s（镜头 3，35mm / 63° FOV 高跟背影对称跟拍）：黑曜石镜面地板两侧布满水平红激光，伊莲娜踩 10cm 金高跟精准步入，红光映亮象牙白真丝裙摆。硬切。
- 23.0–28.0s（镜头 4，85mm / 28° FOV 侧脸逆光）：走廊尽头哥特拱门透出冷白顶光，伊莲娜眼神平静锁定前方（自然眨眼，双唇闭合）。
4. 画质与音频（无旁白无音乐）：黑曜石倒影与丝绸红光反射锐利。[音效] 0–12s 电梯风啸；12.8s 液压锁死+“DING”；14.5s 防爆门泄压“PSSSHHH”；17–28s 寂静空间高跟鞋敲击黑曜石回响。
5. 正面约束：仅伊莲娜 1 人；袋口保留小白色羽毛；无背景配乐。
```

---

#### Block 14｜买家怀表 00:39、机械黑鸦苏醒与哥特祭坛全景建立（`26s · 4 镜硬切` · 原 S36–S38）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，暗部细节保留不死黑，180 度快门。
1. 场景背景：第 14 段，26 秒，地下五层黑红白哥特棋盘祭坛（@loc_gothic_bunker_v1），4 个镜头硬切。伦敦买家合上 00:39 银怀表，机械黑鸦红眼苏醒，冷白单顶光全景建立，伊莲娜步入。
2. 参考素材：@char_tribunal_image_v1（严格仅限 2 名男性 + 1 只仿生黑鸦：老钱买家戴黑羊皮手套与金丝圆眼镜、海因里希额角冒冷汗、机械黑鸦）；@char_elena_video_v1；@loc_gothic_bunker_v1（黑枯木岩壁、10 米深红天鹅绒幕布、双白鹿头骨、发光水晶棋盘正中白皇后空槽；唯一冷白正顶聚光灯）。
3. 光学与逐秒动作：
- 0.0–9.0s（镜头 1，85mm / 28° FOV 明暗近景）：黑羊皮手套“啪”地合上显示“00:39”的银怀表；镜头微抬，仅见买家冷峻侧脸与身后冷汗直流的海因里希（严格 2 名男性），买家开口（仅他动嘴）：“Thirty-nine seconds. Let us see if Geneva's reputation survives the stairs.”，随即两人转头望向入口。硬切。
- 9.0–15.5s（镜头 2，85mm / 28° FOV 棋盘边缘微距）：黑暗中发光水晶棋盘边缘蹲着碳纤维仿生黑鸦，红光眼“嗡”地苏醒对焦，金属乌喙微张。硬切。
- 15.5–17.5s（镜头 3，24mm / 84° FOV 对称大师全景——首秒勘景）：唯一冷白正顶聚光灯直照中央发光水晶棋盘，四周黑枯木岩壁与 10 米深红天鹅绒幕布保留肌理，两座白鹿头骨对称矗立，地面红激光纵横。
- 17.5–26.0s（镜头 3 延续）：@char_elena_video_v1 从左侧深影拎蓝袋从容步入顶光边缘，海因里希与买家在右侧阴影静候。
4. 画质与音频（无旁白无音乐）：羊皮手套纹理、天鹅绒绒毛与碳纤维羽毛质感清晰。[音效] 1.8s 怀表“SNAP”；10.5s 黑鸦伺服马达“WHIRR”；16.0s 极低频管风琴单音环境嗡鸣。[对白] 4.2–8.2s Buyer。
5. 正面约束：严格 2 名男性 + 1 名女性 + 1 只黑鸦，绝不出现第 3 名男性；唯一冷白顶光。
```

---

### ACT IV：地下五层哥特审讯与神迹反杀（`Block 15 – 18`，`113s`）

#### Block 15｜跨过血海红线、落座白皇后格与黑鸦红警探测（`27s · 4 镜硬切` · 原 S39–S41）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门真实质感。
1. 场景背景：第 15 段，27 秒，地下五层哥特棋盘祭坛（@loc_gothic_bunker_v1），4 个镜头硬切。伊莲娜精准跨过红线将蓝方块嵌入棋盘“白皇后”格；黑鸦探针伸入透明虚空，发现 +2.0mm 越位与淀粉、染发剂异常。
2. 参考素材：@char_elena_video_v1；@char_tribunal_image_v1（黑鸦）；@prop_klein_cube（#002FA7 底座 + 4 根红激光，右前偏 2mm，内部全透明空气）；@loc_gothic_bunker_v1。
3. 光学与逐秒动作：
- 0.0–8.5s（镜头 1，28mm / 75° FOV 贴地滑轨）：10cm 金高跟精准踩在两条致命红激光缝隙上，镜头升起至白鹿头骨旁，伊莲娜将蓝袋放在棋盘边。硬切。
- 8.5–17.5s（镜头 2，35mm / 63° FOV 90° 垂直顶拍）：伊莲娜双手捧出 @prop_klein_cube（6cm 白鸽羽悄悄留在旁边蓝袋口），垂直嵌入正中“白皇后”凹槽；四束微米红激光射向黑暗，框出全透明空气。硬切。
- 17.5–23.5s（镜头 3，85mm / 28° FOV 黑鸦微距）：黑鸦跳上棋盘边缘，伸出银色嗅觉探针刺入空虚空；肉眼可见右前红激光向右微偏 2 毫米。硬切。
- 23.5–27.0s（镜头 4，50mm / 47° FOV 悬浮全息屏）：半空全息光谱界面绿波炸成猩红锯齿，清晰显示 `TRACE STARCH: DETECTED / BLUE DYE RESIDUE: DETECTED / LASER OFFSET: +2.0 mm`，买家与海因里希在虚焦后景一震。
4. 画质与音频（无旁白无音乐）：水晶折射与金属探针细节锐利。[音效] 0–8s 激光嗡鸣与高跟落步；14.0s 磁吸重响“KA-WHUMMM！”；20.5s 探针伸出；24.0s 红警“BEEP-BEEP-BEEP”。
5. 正面约束：蓝方块内 100% 透明空空气（无冰块无晶体）；全息屏报错文字清晰无乱码。
```

---

#### Block 16｜伦敦买家致命质询 & 伊莲娜牛津腔反杀前半（`30s · 3 镜硬切` · 原 S42–S43 前半）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门，Acting Skill 6 准则。
1. 场景背景：第 16 段，30 秒，地下五层哥特棋盘祭坛（@loc_gothic_bunker_v1），3 个镜头硬切。买家捏着红警全息屏叫停汇款质询淀粉、染发粉和 2mm 偏移，伊莲娜在冷白顶光下用牛津腔抛出“1960 年克莱因就在尼斯炸薯条酒馆旁封存此作”的开篇反杀。
2. 参考素材：@char_tribunal_image_v1（仅限老钱买家 + 海因里希 2 名男性）；@char_elena_video_v1（冷峻牛津腔音色锁定）；@loc_gothic_bunker_v1（单一冷白正顶聚光灯）。
3. 光学、第一轴线与逐秒动作：
- 0.0–12.0s（镜头 1，50mm / 47° FOV 第一轴线双人反打，买家在右、海因里希在后）：买家黑手套拇指摩挲红警平板边缘（手不离物），半摘金丝眼镜眯眼盯向左侧伊莲娜；海因里希面如死灰僵立；买家冷静质问：“Twelve seconds. Hold the wire. Why does 1960 Nice harbor air contain potato-starch traces, blue dye residue, and a two-millimeter laser offset?”（海因里希闭嘴发颤）。硬切。
- 12.0–16.0s（镜头 2，50mm / 47° FOV 棋盘与伊莲娜反应）：伊莲娜半边面孔隐在可读深影里，眼神如钢钉死锁买家眉心（自然眨眼一次，绝不呆滞），右手食指与中指轻轻搭上发光水晶棋盘边缘。硬切。
- 16.0–30.0s（镜头 3，85mm / 28° FOV 缓慢稳推轨特写）：伊莲娜下颌微抬半英寸，面无一丝慌乱，在说到“frites tavern”时指尖轻敲水晶桌面“哒”，一气呵成念出前半句：“In 1960, Yves Klein sealed this void next to a dockside frites tavern. Sixty years of geomagnetic drift bends Lorentz fields by 2.0 millimeters.”，保持冷漠微停顿。
4. 画质与音频（无旁白无音乐）：皮肤毛孔、眼波微动、真丝肩带随呼吸起伏清晰。[环境音] 低频电流底噪。[音效] 23.8s 指甲敲水晶“哒”。[对白] 1.5–11.5s Buyer；16.5–29.5s Elena（牛津腔口型精准同步）。
5. 正面约束：仅限 2 名男性 + 1 名女性；唯一冷白正顶聚光灯；无背景配乐。
```

---

#### Block 17｜“深圳高仿论”收尾、遮挡换轴线与虚空静电悬浮神迹（`28s · 5 镜硬切` · 原 S43 后半–S45）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门，双轴线遮挡切换。
1. 场景背景：第 17 段，28 秒，地下五层哥特棋盘祭坛（@loc_gothic_bunker_v1），5 个镜头硬切。伊莲娜一句“笔直的激光只有深圳高仿才有”压制全场，通风口送风吹落袋口白鸽羽毛，镜头借黑鸦侧翼遮挡切入 180° 第二对称轴线，白羽在红激光纯空虚空正中心稳稳静电悬浮。
2. 参考素材：@char_elena_video_v1；@char_margaux_image_v1（仅天花板铁栅栏后一闪的银色相机反光）；@prop_klein_cube（四红激光框住透明空虚空，右前偏 2mm）；@loc_gothic_bunker_v1。
3. 光学、遮挡换轴线与逐秒动作：
- 0.0–6.5s（镜头 1，85mm / 28° FOV 伊莲娜近景）：伊莲娜两指轻点右下角微偏 2mm 的红激光束，嘴角留下一抹极克制笑意残余：“Dead-straight lasers only exist on Shenzhen replicas, sir.”。硬切。
- 6.5–11.5s（镜头 2，85mm / 28° FOV 仰摇接俯摇）：通风口百叶轻晃送风（隐约见铁栅后银色徕卡反光），镜头下摇回伊莲娜脚边备份蓝袋口——气流掀起边缘 6cm 纯白鸽子羽毛吹向棋盘中央。硬切。
- 11.5–14.5s（镜头 3，40mm / 57° FOV 遮挡换轴线）：镜头贴黑曜石桌面平稳横移，掠过机械黑鸦立起的黑曜石侧翼完成短暂全屏遮挡（12.5–13.3s），无缝切入居中 180° 第二对称轴线！
- 14.5–22.5s（镜头 4，40mm / 57° FOV 对称居中大师镜头）：6cm 纯白鸽子羽毛飘进 @prop_klein_cube 上方 4 根红激光框住的纯透明虚空正中心，受静电与微流托举，第 19.0s 彻底悬停于几何正中心，细小绒毛极轻颤动（内部 100% 空虚空，绝无冰块或晶体！）。硬切。
- 22.5–28.0s（镜头 5，85mm / 28° FOV 圣洁特写）：冷白手术顶光直射悬停白羽，在黑曜石与深红天鹅绒背景下发出柔白微光。
4. 画质与音频（无旁白无音乐）：羽毛绒毛丝缕分明。[音效] 7.5s 通风管微风。[动作音效] 19.0s 起通风口百叶极轻金属震颤与玻璃罩微弱静电嗡鸣（纯物理声学共鸣，绝无任何配乐或人声）。[对白] 0.5–6.0s Elena。
5. 正面约束：蓝方块内除 1 根 6cm 白鸽羽外空无一物（严禁冰块或发光水晶）；镜头 4/5 无人遮挡中心。
```

---

#### Block 18｜全息屏 `0.000 g` 绿灯、老钱买家摘镜放款 8000 万欧 & 转身退场（`28s · 4 镜硬切` · 原 S46–S48）

```text
[风格前缀] Kodak Vision3 500T 变形宽银幕 2.39:1，180 度快门真实质感。
1. 场景背景：第 18 段，28 秒，地下五层哥特棋盘祭坛（@loc_gothic_bunker_v1），4 个镜头硬切。白羽倒影掠过黑鸦红眼，全息屏翻绿 `VERTICAL ACCELERATION: 0.000 g`，老钱买家震颤摘镜释放八千万欧元，伊莲娜拎起空蓝袋转身步入黑暗。
2. 参考素材：@char_tribunal_image_v1（买家 + 海因里希 + 黑鸦）；@char_elena_video_v1；@loc_gothic_bunker_v1。
3. 光学与逐秒动作：
- 0.0–7.5s（镜头 1，85mm / 28° FOV 黑鸦与全息屏特写）：白羽柔影掠过黑鸦红眼，全息屏瞬间由红转亮翠绿，清晰显示：`VERTICAL ACCELERATION: 0.000 g (WITHIN DISPLAY RESOLUTION) / LEVITATION EVENT: VERIFIED`；地面所有红激光“嗡”地同步转成冷白。硬切。
- 7.5–18.0s（镜头 2，50mm / 47° FOV 伦敦买家近景）：买家瞳孔倒映白羽光芒，黑手套双手微颤摘下金丝圆眼镜，按下加密卫星令牌绿色确认键，朝伊莲娜微俯首敬畏低语：“Suspended in the void... Magnificent. Eighty million euros released.”（后景海因里希长舒一口气）。硬切。
- 18.0–24.0s（镜头 3，50mm / 47° FOV 伊莲娜近景）：伊莲娜眼神毫无波澜，弯腰拎起空了的克莱因蓝纸袋，淡淡道：“Pleasure doing business.”。硬切。
- 24.0–28.0s（镜头 4，35mm / 63° FOV 背影长廊）：伊莲娜背对八千万欧元踩 10cm 金高跟笔直走入电梯走廊黑暗。
4. 画质与音频（无旁白无音乐）：皮肤微颤与眼镜反光真实。[音效] 2.5s 翠绿水晶提示音“DINGGGG”；3.5s 激光转白稳压声；12.5s 卫星令牌轻滴；25.0s 高跟鞋声渐远。[对白] 13.0–17.6s Buyer；20.5–22.5s Elena。
5. 正面约束：全息屏文字清晰为 `VERTICAL ACCELERATION: 0.000 g (WITHIN DISPLAY RESOLUTION)` 与 `LEVITATION EVENT: VERIFIED`；严格 2 男 1 女 1 鸦。
```

---

### EPILOGUE：荒诞余波与 2D 丝网印闭环（`Block 19 – 20`，`52s`）

#### Block 19｜船坞撒钱狂欢、FT 头版大乌龙 & 免税大道三人换装并肩（`26s · 4 镜硬切` · 原 S49–S51）

```text
[风格前缀] Vision3 250D 日光观感，变形宽银幕 2.39:1，180 度快门真实质感。
1. 场景背景：第 19 段，26 秒，从夕阳红蓝干船坞切至次日清晨现代混凝土免税大道（日景），4 个镜头硬切。金克丝与克洛伊船坞撒钱喷香槟，《THE VENICE LEDGER》头版大乌龙，次日清晨伊莲娜、瓦伦蒂娜、克洛伊换装并肩迈出旋转门，耳机里海因里希崩溃追问。
2. 参考素材：@char_jinx_image_v1（+ 戴粉墨镜的白贵宾犬）；@char_chloe_image_v2；@char_elena_video_v1（换装为宽松象牙白高定西装套装，左耳透明耳机）；@char_valentina_image_v1（换装为宽松克莱因蓝长风衣）；@loc_taxfree_zone_v1。
3. 光学与逐秒动作：
- 0.0–8.5s（镜头 1，35mm / 63° FOV 船坞夕阳中景）：金克丝坐在修好的购物车顶向蓝天抛撒欧元纸币，白贵宾犬戴着瓦伦蒂娜的芭比粉墨镜开心汪叫，克洛伊拧开香槟喷出漫天泡沫。硬切。
- 8.5–15.0s（镜头 2，85mm / 28° FOV 报摊石板推镜）：一捆鲑鱼粉《THE VENICE LEDGER》甩在威尼斯石板地上，镜头推近头版黑白照（玛格特拍下的伊莲娜跃过干船坞、群鸽乱飞），粗黑标题清晰：“HEIRESS STAGES RADICAL PARKOUR PROTEST AGAINST ART FINANCE”。硬切。
- 15.0–26.0s（镜头 3/4，35mm / 63° FOV 免税大道跟拍）：现代旋转玻璃门转出——换上象牙白西装的伊莲娜稳步走出；穿克莱因蓝大衣的瓦伦蒂娜与粉白格纹的克洛伊丝滑并入左右同步前行；伊莲娜轻触耳机，双唇紧闭静止（绝不张嘴），耳机传出海因里希崩溃质问。
4. 画质与音频（无旁白无音乐）：新闻纸纤维、香槟泡沫与高定西装垂坠质感清晰。[音效] 6.5s 香槟“POP！”；9.0s 报纸砸地；18.0s 整齐脚步。[对白] 20.5–25.5s 仅耳机画外音 Heinrich 崩溃嘶喊（画面三人全部闭嘴前行）: {Elena! Geneva HQ is losing their minds—how did you engineer feather levitation?!}。
5. 正面约束：白贵宾犬戴粉墨镜；头版标题无乱码；第 15–26s 三位主角已换装且全程闭嘴。
```

---

#### Block 20｜90° 侧影尺规行进、3D 坍缩 2D 丝网版画定格切黑（接 Card 10）（`26s · 3 镜硬切` · 原 S52–S54）

```text
[风格前缀] Vision3 250D 日光实拍质感向 12fps 现代时尚杂志 2D 粗粝 Risograph 丝网版画平滑坍缩，2.39:1 宽银幕。
1. 场景背景：第 20 段（收官），26 秒，现代蓝色几何混凝土免税大道（@loc_taxfree_zone_v1）。伊莲娜耳机画外音报销完“六万欧 + 贝隆生蚝 + 三欧五十海盐薯片（没发票）”后，画面定格为 2D 丝网版画海报后干脆切黑，随即接入 Card 10 作为唯一完整纯蓝片尾卡。
2. 参考素材：@char_elena_video_v1（象牙白西装）；@char_valentina_image_v1（克莱因蓝大衣）；@char_chloe_image_v2（粉白格纹西装）；@loc_taxfree_zone_v1（现代蓝色几何墙面标有“TAX-FREE ZONE”）。
3. 光学与逐秒动作（90° 侧影 & 嘴唇铁律）：
- 0.0–11.0s（镜头 1，50mm / 47° FOV 90° 正侧面横向跟拍）：三人严格保持 1.5 米等距步幅，各拎钴蓝与粉白购物袋从左向右走过“TAX-FREE ZONE”蓝色几何墙前；三人侧脸闭嘴目视前方；第 7.0s 起实拍光影扁平化为硬边色块，无缝坍缩成 2D 粗糙粉笔肌理克莱因蓝丝网版画。无缝接续。
- 11.0–21.0s（镜头 2，12fps 2D 丝网印刷动画）：三个拉长至九头身的无脸极简剪影女郎在冷灰天空与“TAX-FREE ZONE”钴蓝方块前踩韵律步态并肩前行，购物袋边露出欧元绑带与“CRISPS”薯片袋一角；第 19.0s 骤然定格为静态丝网版画海报。硬切。
- 21.0–26.0s（镜头 3，2D 海报定格 → 干脆切黑）：2D 丝网版画海报纸张颗粒微闪 3.5 秒，第 24.5s 至 26.0s 保持静态定格后干脆切黑（随后由 `Card 10` 承担唯一完整 `#002FA7` 纯蓝片尾卡）。
4. 画质与音频（无旁白无音乐）：2D 纸张粗粝网点颗粒与纯正 #002FA7 蓝无偏紫。[音效] 0–18s 整齐鞋跟踏步；19.0s 定格“CLICK！”；24.5s 印刷油墨定格微响。[对白] 全程三人嘴唇闭合静止，仅画外耳机低语：
  - 2.0–9.5s Elena: {Trade secret. Approve my expense sheet: €60,000 fee, and one crushed Belon oyster.}
  - 14.0–18.8s Elena: {...Plus one bag of sea-salt crisps. Three euros fifty. No receipt.}
5. 正面约束：三人保持 1.5m 等距 90° 侧影，绝不回头或张嘴；#002FA7 纯蓝无偏紫；第 26 秒干脆切黑。
```

---

## 五、交付前核验 Gate（V3.7 实操清单）

> 资产需逐张人工目视抽检并完成小样测试后再进入批量生成；以下为交付与投喂前的实操核验门禁：

- [ ] 统一采用全画幅对角 FOV 表；不再出现 14mm/94°、18mm/84°、16mm/88° 等错配。
- [ ] 日景/黄昏/地下场景按 250D/500T 风格分别处理，不把胶片型号当作精确生成参数。
- [ ] 角色精修不改变身份、服装剪裁、配色与构图；不声称由 2D 提示词生成真实 3D/PBR 贴图。
- [ ] 20 个 Master Block 已拆成独立短镜头，复杂动作拆分并有首帧/尾帧约束。
- [ ] 激光 15° → 2mm → +2.0mm 检测状态连续。
- [ ] 淀粉与蓝染料残留在 Block 11 有来源，在 Block 15/16/Card 09 有一致证据名称。
- [ ] 羽毛由袋口进入空域，悬浮由气流减弱与静电效果呈现，不宣称真实零重力。
- [ ] Block 14 怀表、Block 15 时长、Block 16 “Twelve seconds”匹配。
- [ ] Block 20 以海报切黑结束，Card 10 是唯一完整纯蓝片尾卡。
- [ ] 角色名统一 Margaux；Chloé 左脚鞋状态、Jinx 狗只数量、三人次日换装连续。
- [ ] 所有 UI、字幕、新闻标题在后期排版并逐字校对。
- [ ] 逐张检查 23 张原始资产的身份/服装/场景一致性；未完成目视检查前不得标记资产审核“通过”。
