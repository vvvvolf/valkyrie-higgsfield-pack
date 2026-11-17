# 《免税区女武神：蓝方块越位》GPT / Higgsfield 资产索引表（V3 统一版）

将本仓库链接丢给 GPT 后，请按以下对照表将 `assets/` 目录中的参考图绑定至 [`V3_MASTER_SCRIPT_AND_PROMPTS.md`](./V3_MASTER_SCRIPT_AND_PROMPTS.md) 与 [`V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md`](./V3_ATOMIC_SHOTS_88_EXECUTION_TABLE.md) 里的 `@` 标签：

## 1. 角色与核心道具资产（10 张）
| 提示词 `@` 标签 | 对应图片文件 (`assets/`) | 说明与绑定边界 |
| :--- | :--- | :--- |
| `@char_elena_video_v1` | `char_elena.png` | 建议先用此图生成 4s 含呼吸/眨眼视频角色卡，再喂给正片；锁定象牙白丝裙、翠绿腰带、10cm 金高跟 |
| `@char_chloe_image_v2` | `char_chloe_v2.png` | 忽略白底三视图；锁定粉短发、荧光黄墨镜、粉白格纹装与厚底白老爹鞋（Block 02–12 左脚失鞋仅穿白袜） |
| `@char_valentina_image_v1` | `char_valentina.png` | 忽略白底三视图；锁定齐下巴黑波波头、芭比粉猫眼墨镜、亮面芭比粉漆皮风衣 |
| `@char_margaux_image_v1` | `char_margaux.png` | 忽略白底三视图；锁定棕色软呢帽、格纹粗花呢西装、徕卡 M3 旁轴相机（全片统一拼写 `Margaux`） |
| `@char_jinx_image_v1` | `char_jinx.png` | 忽略白底三视图；锁定 2 米 `#002FA7` 蓝脏辫、黄铜护目镜、弹簧高跷靴（配唯一 1 只白贵宾犬） |
| `@char_buyer` | `char_buyer.png` | 从 `char_tribunal.png` 独立裁切，锁定伦敦老钱买家（黑羊皮手套、银灰背头、双排扣黑大衣），防止多人同框串脸 |
| `@char_heinrich` | `char_heinrich.png` | 从 `char_tribunal.png` 独立裁切，锁定海因里希（圆框金丝眼镜、刺绣黑礼服、手持平板） |
| `@char_raven` | `char_raven.png` | 从 `char_tribunal.png` 独立裁切，锁定碳纤维仿生黑鸦（红光眼、金属乌喙） |
| `@char_tribunal_image_v1` | `char_tribunal.png` | 地下审判庭三人原始合成参考（仅作全景站位参考，单镜生成优先用上方三张独立裁切图） |
| `@prop_klein_cube` | `asset_00_klein_cube.png` | `20cm × 20cm` 哑光 `#002FA7` 底座 + 透明玻璃罩 + 四角 1mm 红激光；内部 **100% 透明空虚空**，**严禁冰块或蓝水晶** |

## 2. 四大片场与关键场景参考（16 张）
| 提示词 `@` 标签 | 对应图片文件 (`assets/`) | 锁定内容 |
| :--- | :--- | :--- |
| `@loc_venice_arcade_v1` | `scene_venice_arcade.png`, `ref_01_elena_arch.jpg`, `ref_02_slide_chloe.jpg`, `ref_03_midair_seal.jpg`, `ref_04_valentina.jpg` | 威尼斯圣马可白石免税拱廊（仅锁结构与右上方单一烈日，不沿用参考图构图；250D 日景观感） |
| `@loc_red_drydock_v1` | `scene_red_drydock.png`, `ref_05_jinx_redblue.jpg`, `ref_06_margot_chase.jpg`, `ref_07_sector04.jpg` | `SECTOR 04` 红锈油罐干船坞 + 纯蓝晴空撞色（250D 高反差日景） |
| `@loc_red_tanks_alley_v1` | `ref_08_act3_forgery.jpg`, `ref_09_act3_taser.jpg` | 黄昏熔金逆光红锈油罐铁轨死胡同（500T 暖逆光；对应 Block 09–12） |
| `@loc_gothic_bunker_v1` | `scene_gothic_bunker.png`, `ref_10_act4_altar.jpg` | 地下五层黑红白哥特棋盘祭坛 + 唯一冷白正顶聚光灯（Zenith Spotlight；500T 低照度） |
| `@loc_taxfree_zone_v1` | `ref_11_epilogue_2d.jpg`, `ref_12_taxfree_zone.jpg`, `ref_13_chloe_plaid.jpeg` | 现代 `TAX-FREE ZONE` 免税大道与 2D 丝网印坍缩收尾参照（250D 日景转 2D Risograph） |
