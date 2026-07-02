# 用户照片库

这个 skill 支持长期保存用户本人形象照片，用于后续生成主理人封面、口播封面和个人品牌封面。

## 存放位置

照片放在：

`assets/user-photos/`

命名格式：

`YYYYMMDD-brief-description.ext`

示例：

- `20260701-front-facing-black-shirt.jpg`
- `20260701-side-profile-office.png`
- `20260701-speaking-gesture.webp`

如果一次提供多张照片，按场景命名，不要只叫 `photo1.jpg`。

## 保存规则

- 保留原始照片，不要覆盖。
- 如果需要裁切、去背景或风格化，另存新文件，文件名加 `cropped`、`cutout` 或风格名。
- 如果用户提供的是临时对标图而不是本人照片，放入 `assets/reference-covers/`，不要混进用户照片库。
- 以后调用用户照片时，优先使用最近一次保存的清晰正脸照；如果封面需要动作感，再选手势或半身照。

## 使用规则

人物封面优先保留真实识别度：

- 眼睛和脸部清楚。
- 不要过度磨皮或换脸到不像本人。
- 姿态要服务标题情绪：观点类用笃定表情，吐槽类用夸张表情，故事类用沉静表情。
- 如果用户照片质量差，先说明限制，再建议补拍：正脸、半身、干净背景、自然光、无遮挡。

## 生图提示词补充

使用用户照片时，在提示词里加：

```text
Use the provided portrait as the identity reference. Preserve facial identity and natural skin texture. Create a clickable video cover composition around this person.
```

如果模型可能改脸，建议生成背景和封面布局后，用设计工具把用户照片抠图叠加进去。
