# 城市扫描线幻景

`urban-scanline-mirage` 是一个用于城市、街道和建筑照片的 Codex Skill。它保留人物及其行动关系，把其余环境重构为来源于原图色彩的矩形色域与细密横向扫描线。

## 快速开始

上传一张原图，然后输入：

```text
使用 $urban-scanline-mirage 修改这张照片。
```

Skill 会自动分析主体与空间，调用可用的图像编辑工具生成结果，并在交付前检查人物完整性和扫描线效果。

## 适合的原图

- 城市街道、巷道、市场、车站、广场和桥下空间；
- 现代或老建筑、立面、停车区和公共空间；
- 画面中有一位人物或一个明确行动群组；
- 人物正在步行、等待、骑行、修理、打伞、提物或进行其他可见动作。

## 核心效果

- 人物、动作物品、必要连接、脚下接触区和真实阴影保持摄影质感；
- 天空、地面、建筑和其他背景全部转化，不残留大片写实区域；
- 环境由少量大矩形色域、横条和必要的竖向锚点构成；
- 色彩取自原图，不套用固定配色；
- 每个色域内部使用独立的发丝级横向微层理，而不是全图统一滤镜；
- 缩小看先读到人物和大色域，放大后才能看见细密、清晰的水平色层。

## 结果检查

合格结果应满足：

1. 人物和动作物品没有变形、放大、复制或位置漂移；
2. 原场所仍可通过体块、地平线、色彩节奏和少量锚点被认出；
3. 背景不再依赖车辆、树叶、门窗、灯具等完整自然轮廓；
4. 横线纤细、紧密、低对比、有局部色差，不像 CRT 网格或横向拖影；
5. 天空和地面与建筑具有相同的转化程度，但信息密度更低。

## 生成不理想时

| 问题 | 修正方向 |
| --- | --- |
| 像照片上覆盖横线 | 重新结构化天空、地面和次要物体，不要增加全局线条 |
| 色块太干净 | 在各色域内部增加近邻色变化、局部断点和不均匀层理 |
| 横线像模糊拖影 | 恢复发丝级行层定义，降低柔化和连续涂抹感 |
| 画面像杂乱马赛克 | 合并小碎块，减少色域数量，保留更大的主色区域 |
| 柱子或树干太多 | 合并重复竖向结构，只保留最低限度的空间锚点 |
| 人物发生变形 | 扩大人物与动作物品的保护区域，只重新生成环境层 |

## 安装

### macOS / Linux

```bash
mkdir -p "$HOME/.codex/skills"
git clone --depth 1 https://github.com/ximisins-collab/urban-scanline-mirage.git "$HOME/.codex/skills/urban-scanline-mirage"
```

### Windows PowerShell

```powershell
$skillRoot = Join-Path $env:USERPROFILE '.codex\skills'
New-Item -ItemType Directory -Force -Path $skillRoot | Out-Null
git clone --depth 1 https://github.com/ximisins-collab/urban-scanline-mirage.git (Join-Path $skillRoot 'urban-scanline-mirage')
```

也可以[下载 ZIP](https://github.com/ximisins-collab/urban-scanline-mirage/archive/refs/heads/main.zip)，解压后把包含 `SKILL.md` 的文件夹放到：

```text
~/.codex/skills/urban-scanline-mirage
```

## 更新

```bash
git -C "$HOME/.codex/skills/urban-scanline-mirage" pull --ff-only
```

## 运行要求

- 需要支持 Skill 调用的 Codex 环境；
- 需要可用的 `imagegen` 或等效图像编辑能力；
- 本仓库不包含图像模型、API 密钥或生成额度。

## 示例图片

示例图待补充。建议上传 3–5 组已获公开许可的“原图 / 生成结果”对照图片，并在上传前清理不必要的个人信息和图片元数据。

## 许可证

[MIT License](LICENSE)
