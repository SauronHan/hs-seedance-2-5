# 光学度数、物理法则与空间锁定规范 (Optics, Physics & Spatial Locks)

本参考文档是 `hs-seedance-2-5` 的高阶控制子模块，专为消除 AI 视频生成中的“镜头焦距漂移、塑料感/无重力物理违和、角色瞬移与空间混乱”而设计。

在 Seedance 2.5 的 **4 段式导演结构** 中，本模块内容作为 **【分镜头与时间轴剧情描述】** 与 **【画面风格与声音全局补充】** 的精细控制增强，无需破坏原 4 段式框架。

---

## 第一部分：10 级 FOV 对角线视场角系统 (Optics System)

### 1. 视听叙事意图优先与 FOV 度数系统 (Narrative Intent First, FOV as Assist)
- **叙事意图为首要主源**：摄影机焦段与视场的核心功能是塑造人物心理距离、环境压迫感或亲密对峙感。提示词应优先以自然语言描述可见的**镜头透视意图**（如“环境包裹人物展现渺小感”、“背景强烈纵深压缩凸显对峙紧迫感”）。
- **FOV 度数作为工程对齐辅助**：在扩散模型中，直接写“85mm”容易被误判为器材型号词。**使用对角线视场角度数（Diagonal FOV）配合机位距离描述，是辅助模型稳定渲染出预期透视效果的推荐工程假设，而非绝对物理测绘标准**。先定叙事意图，再附推荐度数，最后按需施加局部防漂移锁。


| 等级 | FOV 度数 | 镜头性质 | 适用场景与内容对齐 | 机位物理距离 |
|---|---|---|---|---|
| 1 | **180°** | 极限鱼眼 / 门镜 | 门镜窥视、管涌视角、极限眩晕、监控畸变 | 0.1–0.3m |
| 2 | **135°** | 极限沉浸超广角 | 灾难全景、飞船驾驶舱广域包裹、极限极限运动 | 0.3–0.5m |
| 3 | **107°** | 广角直线透视 (Rectilinear) | 宏大室内空间、建筑全景、强化空间纵深感 | 0.5–0.8m |
| 4 | **84°** | 经典电影广角 (Cuarón 广角) | 贴身跟随、全身环境调度、交代人物与宏大背景关系 | 1.0–1.5m |
| 5 | **63°** | 广角偏标准 (35mm 等效) | 街头纪实、双人对话环境半身、自然走道跟随 | 1.8–2.5m |
| 6 | **47°** | 标准人眼视角 (50mm 等效) | 最稳固客观视角、标准剧情交流、零透视畸变 | 3.0–5.0m |
| 7 | **35°** | 微长焦自然肖像 | 单人胸上肖像、半身对话、柔和背景分离 | 3.5–5.0m |
| 8 | **29°** | 短长焦人像特写 | 情绪特写、面部特征聚焦、背景奶油般虚化 (Creamy Bokeh) | 4.0–6.0m |
| 9 | **18°** | 经典长焦压缩 | 强烈纵深压缩、背景压平逼近、极窄焦点孤立眼神 | 6.0–8.0m |
| 10 | **8°** | 超远摄观察 / 狗仔窥视 | 极度远距离监视、体育转播质感、前景严重虚焦遮挡 | 20.0–25.0m |

### 2. 常用 FOV 语言模板（可直接并入提示词第四段）

#### 【47° 标准人眼视角】
```text
47° diagonal field of view, standard normal lens character, camera 3 to 5 meters from subject, natural human-eye perspective. Zero obvious distortion, natural face and body proportions, comfortable depth of field, background readable but not exaggerated, classic grounded cinema framing.
（47度对角线视场角，标准正常人眼透视，机位距主体3-5米。无畸变，人物面部与身体比例自然，景深舒适，背景清晰可辨但不过分夸张，经典沉稳的电影质感构图。）
```

#### 【84° 经典环境广角】
```text
84° diagonal field of view, classic wide-angle lens character, camera 1 to 1.5 meters from subject. Strong natural perspective expansion, foreground subject looms larger, environment remains visible to the frame edges, deep readable spatial context, straight architectural lines stay rectilinear, no fisheye curve.
（84度对角线视场角，经典广角特性，机位距主体1-1.5米。自然透视扩张感，前景人物存在感增强，四周环境至画幅边缘清晰延展，建筑直线保持平直，无鱼眼弯曲。）
```

#### 【29° 短长焦人像特写】
```text
29° diagonal field of view, short telephoto portrait lens character, camera 4 to 6 meters from subject. Close framing achieved through lens reach, not physical proximity. Subject is razor-sharp, background dissolves into creamy soft bokeh, subject pops clearly from the environment.
（29度对角线视场角，短长焦人像质感，机位距主体4-6米。通过长焦望远而非物理贴近实现紧凑构图。主体极其锐利清晰，背景消融为奶油般柔和光斑，人物与环境鲜明分离。）
```

#### 【18° 经典长焦背景压缩】
```text
18° diagonal field of view, classic telephoto lens character, camera 6 to 8 meters from subject. Strong background compression, distant elements appear stacked closer behind the subject, razor-thin focus isolates the eyes, foreground and background melt into soft bokeh.
（18度对角线视场角，经典长焦压缩特性，机位距主体6-8米。背景产生强烈空间压缩，远景元素被拉近贴在主体身后，极浅景深精准咬住眼眸，前后景彻底柔化。）
```

#### 【8° 超远摄窥视视角】
```text
8° diagonal field of view, super-telephoto observation lens character, camera 20 to 25 meters from subject. Extreme background compression, background flattened into a soft color wash. Foreground occlusion frames the subject as oversized dark blurred bokeh shapes occupying 30% of the frame.
（8度对角线视场角，超长焦远距离窥视，机位距主体20-25米。极度空间压缩，背景压平为柔和色块。前景带有大面积深色失焦遮挡物（占据画幅下部30%），呈现从掩体后偷拍窥视的质感。）
```

### 3. 内容与 FOV 对齐法则 (Content-FOV Alignment)
- **人像肖像 → 选用长焦 (29° / 18°)**：获得稳定的五官比例与纯净背景；
- **环境动作与群像调度 → 选用广角/标焦 (84° / 47°)**：展现全身肢体、移动轨迹与空间纵深；
- **微距细节 (Macro/Detail) → 单独作为独立镜头处理**，严禁在一个时间戳内强行混合“宏大广角环境”与“眼球微距特写”（必然引发模型计算崩溃与焦距漂移）。

### 4. 镜头防漂移锁 (Anti-drift Locks)
当生成过程中模型出现镜头乱变（如特写突然拉大成全身，或广角突然变大头照）时，在全局视听补充中加入防漂移锁定句：
- **长焦防漂移锁**：`「No part of this shot becomes wide-angle. Wider framing is achieved by the camera being farther away with the same long-lens reach, not by switching lenses. Background remains compressed in every frame.（本镜头全程严禁变为广角。更大景别仅通过摄影机在相同长焦焦段下退后实现，背景全程保持强压缩与消融状态。）」`
- **广角防漂移锁**：`「No part of this shot becomes telephoto portrait coverage. The environment stays visible around the subject, camera remains physically close, deep readable spatial context maintained.（本镜头全程严禁变为长焦大头照。环境全程环绕主体可见，保持近距离物理构图与大景深环境纵深。）」`

---

## 第二部分：物理引擎约束系统 (Physics Engine)

AI 视频最常出现的违和感是“无质量塑料感、脚滑漂移、物体无惯性瞬移”。在【分镜头与时间轴剧情描述】中必须显性声明物理交互约束：

### 1. 质量、重心与惯性 (Mass & Inertia)
- **起步与刹车**：奔跑与行走必须有重量转移（Heel contact → weight transfer → toe push-off）。严禁角色像传送带上滑动般平移。
- **重物与武器握持**：手臂肌肉必须体现物品自重，手腕角度随重心下沉；挥舞武器必须有加速段、最高速度与减速阻力，严禁瞬时位移。
- **碰撞与反作用力**：推门、撞击、跌倒必须有反弹与身体微小震颤，严禁穿模或弹性如果冻般的虚假变形。

### 2. 流体、雨雪与粒子 (Fluids & Particles)
- **血液与液体物理**：血液不是均匀红色涂料；必须遵循重力：`「Blood clings, drips, smears, pools, and stains along surface textures; droplets travel in parabolic arcs under gravity.（血液沿表面纹理附着、滴落、涂抹并汇聚，血滴在重力下呈抛物线飞溅，带有黏度与重力附着。）」`
- **烟尘风向一致性**：雨滴、雪花、火星、烟雾必须受同一个主导风向矢量驱动；前景、中景、背景烟尘浓度有层次递进。
- **布料与发丝延迟 (Cloth & Hair Lag)**：衣服下摆与长发在剧烈转身时必须具有半拍的物理滞后（Inertial delay），并在停步后产生自然的惯性回摆。

---

## 第三部分：空间防错三锁定与导演例外机制 (Spatial Locks & Directorial Exception)

> **原则**：以下三项锁定是针对 AI 扩散模型常见“人偶漂浮、空间撕裂、死眼恐怖谷”的**强默认工程底线**。  
> 默认情况下所有镜头必须执行；若导演在视听叙事上必须突破（如迟入场悬念、打破第四面墙独白、无地标荒漠），必须通过 `DIRECTORIAL_EXCEPTION` 显式声明艺术理由与技术代偿方案。

### 1. 首帧占位锁 (First Frame Occupancy Lock)
- **强默认规则**：视频的第 0 秒必须明确当前构图内存在的所有角色及其初始空间占位。
- **技术防翻车原因**：AI 模型在第 2–4 秒中途凭空生成新人物时，极易产生画面撕裂、肢体畸形长出或全画幅剧烈抖动。
- **导演例外场景与代偿（迟入场悬念 / 惊喜进门）**：
  - *允许例外*：悬疑恐怖片中威胁从画外阴影缓缓步入背景，或开门揭示新人物。
  - *必须代偿方案*：在第 0 秒明确“人物已身处画框边缘阴影/门扉之后，仅露出衣角或身体轮廓”，或采用“镜头先拍环境空镜，随后运镜摇向门外走入的人物”，避免从完全空白的画幅中凭空撕裂像素。

### 2. 空间地标锁 (Spatial Landmark Lock)
- **强默认规则**：角色必须绑定画面中可见的不可移动硬地标（如铁柱、壁炉转角、吧台边缘、单人沙发），禁止使用模糊介词（“在旁边”）。
- **技术防翻车原因**：缺乏物理锚点会导致模型将人物渲染为无摩擦滑动，产生“传送带平移”假象。
- **导演例外场景与代偿（自然荒原 / 纯黑抽象空间）**：
  - *允许例外*：雪原、荒漠、大海、草地或纯黑心理审讯空间。
  - *必须代偿方案*：使用地表可见纹理区（如“车轮泥泞压痕处”、“冰面裂纹分界点”）、远景水平线或主光投射在地面上的几何明暗交界斑块作为动态参照系。

### 3. 视线与身体朝向解耦锁 (Gaze vs. Body Orientation Lock)
- **强默认规则**：身体朝向与眼动视线独立分写；默认眼神锁定在对手或目标物体上，**严禁目光无故飘向摄影机镜头**。
- **技术防翻车原因**：无意识直视镜头会诱发恐怖谷死眼、面容坍塌。
- **导演例外场景与代偿（打破第四面墙 / 极端主观视角 POV）**：
  - *允许例外*：《纸牌屋》式打破第四面墙独白，或反派逼视镜头直接威胁观众。
  - *必须代偿方案*：必须在提示词中追加高阶眼动生命指令：`「Eyes directly look into the camera lens with intense intelligence; subtle 2-second blink tempo, clear catchlights, micro-saccades around lens center, fully grounded living human presence.（目光直视镜头，带有强烈思考感；自然的2秒眨眼节奏，通透眼神光，绝无呆滞死眼感）」`。

---

## 第四部分：分层静默 QA 自检清单 (Layered Silent QA Checklist)

在将提示词交付执行前，默默完成核对；发现不合规当场修正：

### A. 核心 8 项硬性必检（所有镜头通用）
- [ ] 1. **素材映射精准**：当前镜头引用的 `@图片` 标签全部有据可查且职责明确（外貌/服装/空间）？
- [ ] 2. **空间初始定位**：第 0 秒已安排所有出镜主体，或迟入场镜头已写明阴影边缘代偿方案？
- [ ] 3. **空间地标锚定**：主体绑定了可见硬地标，或自然场景已指定地表纹理/光影参照系？
- [ ] 4. **朝向与视线解耦**：身体朝向与视线方向已明确拆开，无意直视镜头已被排除？
- [ ] 5. **光学叙事意图**：已表达叙事镜头感受，肖像选用了长焦（29°/18°）、动作全景选用了广角（84°/47°）？
- [ ] 6. **物理真实质感**：起步/刹车有重心转移，手持重物显现自重与肌肉阻力？
- [ ] 7. **时间连续与可行**：时间区间无缝衔接（如 0-3s, 3-7s），动作量在指定秒数内物理可行？
- [ ] 8. **音频模式清晰**：准确选定 `DIALOGUE_NATIVE` / `MUSIC_PLAYBACK` / `SILENT_OR_FOLEY` 之一？

### B. 专项情境核对（按需自检）
- [ ] 9. **主光基线与例外**：默认单一主光源方位明确；若采用多光源/舞台光，是否已在操作卡登记导演例外？
- [ ] 10. **防漂移锁触发**：长焦特写加了长焦防漂移句，广角环境加了广角防漂移句？
- [ ] 11. **流体惯性黏度**：血液、雨滴、液体遵循抛物线重力与表面张力，未画成果冻或色块？
- [ ] 12. **微距独立切镜**：眼球特写/手表表盘等微距细节已独立开镜，未与广角大动作混写？
- [ ] 13. **逆光与剪影防平光**：逆光或剪影场景显式声明了“按高光/轮廓曝光，面部允许压入暗部”？
- [ ] 14. **字幕负向彻底**：全局补充中已严明禁止生成任何中英文字幕与水印？
- [ ] 15. **音乐对口型所有权**：音乐场景明确了唯一主唱，背景角色嘴唇锁定闭合（No lip-sync for others）？
- [ ] 16. **密封自包含**：提示词独立完整，无“接上镜动作”等跨文本依赖词？

