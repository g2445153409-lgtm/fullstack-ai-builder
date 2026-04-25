---
name: fullstack-ai-app-builder
description: |
  全栈AI应用快速搭建方法论。帮助非技术背景的创始人、效率工具创造者、企业内部系统搭建者，在没有后端工程师的情况下，快速从想法到上线一个完整的AI驱动全栈应用。

  核心价值：端到端完整路径（需求分析→技术方案→前端→后端→AI集成→部署上线）

  适用场景：
  - "我有个想法，想快速做一个web应用/工具"
  - "怎么快速搭建一个内部系统"
  - "想集成AI能力，但不知道怎么开始"
  - "需要一个简单的数据库系统"
  - "如何快速部署前端页面"
  - "想做一个能处理用户上传文件的应用"
  - "如何集成DeepSeek/通义千问/Gemini等AI API"
  - 用户描述了一个完整的应用场景，询问技术方案

version: "1.0"
author: "AI Development Methodology"
category: ["full-stack", "ai-integration", "web-development"]
tags: ["MVP", "fast-prototyping", "full-stack", "AI", "Supabase", "React", "Vercel"]
---

# fullstack-ai-app-builder：快速搭建全栈AI应用

> **核心哲学**：Andrej Karpathy 说的——"不要一上来就写代码。先用文字把你想做的系统完整描述一遍。"

## 🎯 这个Skill能帮你什么？

你有个想法，但不知道怎么快速把它做成一个真实的web应用？

这个Skill会引导你完整的3阶段过程：

```
第一阶段：想清楚（30分钟）
  ↓ 痛点三问 + 信息收集
第二阶段：设计清楚（30分钟）
  ↓ 技术栈决策 + 数据模型
第三阶段：快速实现（3-6小时）
  ↓ 代码生成 + 配置 + 部署
```

**结果**：你的应用在网上了，可以给用户试用。

---

## 第一阶段：需求清晰化（30分钟）

### Step 1：痛点三问

用这三个问题把你的想法从"模糊"变成"清晰"：

```
Q1: 你（或你的用户）每天/每周重复做什么低效的事？
    → 这是你的痛点

Q2: 如果这件事自动化了，你省了多少时间？带来多少价值？
    → 这是你的价值主张

Q3: 最核心的一个功能是什么？把其他都删掉，只保留这一个。
    → 这是你的MVP（最小可行产品）
```

我会根据你的回答，帮你确认这个想法值不值得做。

### Step 2：信息收集

根据你的项目类型，我会问以下问题：

**企业内部工具类**：
- 使用人数？（1人？10人？100人？）→ 决定架构复杂度
- 现有数据在哪里？（Excel/纸张/微信群？）
- 谁来维护？（有IT？还是业务自己用？）
- 访问方式？（内网Only？外网？手机？）

**个人效率工具类**：
- 数据是否需要跨设备同步？
- 是否需要分享给别人？
- 是否需要AI能力？（提取/分析/生成？）

**对外产品/SaaS类**：
- 用户画像？（国内？海外？技术背景？）
- 商业模式？（免费？订阅？按次付费？）
- 初期DAU预期？（决定是否需要服务器）

### Step 3：确认MVP

我会帮你删掉所有"看起来很cool但实际不必需"的功能，只保留核心的1-2个。

---

## 第二阶段：技术方案设计（30分钟）

### 决策树1：根据用户量选技术

```
你的项目需要多少用户同时使用？

├─ 只有1-3个人用
│  → 单HTML文件 + localStorage（零成本，无服务器）
│
├─ 团队（4-50人）用，需要共享数据
│  ├─ 国内为主 → Supabase（有国内代理方案）
│  └─ 国内外都有 → Supabase（自带全球CDN）
│
└─ 对外产品，用户量不确定
   ├─ 前期验证阶段 → Supabase（免费，够用）
   └─ 规模化后 → 迁移到专用服务器（代码无需大改）
```

### 决策树2：需要什么AI能力？

```
需要AI吗？

├─ 图片识别/OCR 
│  → 通义千问VL（国内快，免费额度大）或 Gemini（更强，需代理）
│
├─ 文字提取/结构化 
│  → DeepSeek（国内直连，性价比最高）
│
├─ 复杂推理/写作 
│  → Claude API 或 GPT-4o（看预算）
│
└─ 不需要AI 
   → 删掉AI，简单就是美
```

### 推荐技术栈（覆盖90%小项目）

| 层次 | 推荐方案 | 为什么 | 免费额度 |
|------|---------|-------|---------|
| 前端 | 单HTML + React(CDN) | 零配置，无需npm安装 | 完全免费 |
| 后端/数据库 | Supabase | PostgreSQL级别可靠，API自动生成 | 500MB存储 |
| AI-图像 | 通义千问VL | 国内速度快，免费额度大 | 100万token/月 |
| AI-文本 | DeepSeek Chat | 国内直连，比GPT便宜90% | 按量计费 |
| 前端托管 | Vercel | 全球CDN，国内也能访问 | 完全免费 |
| CDN加速 | Cloudflare | 套在Vercel前，国内更快 | 完全免费 |

### 数据模型设计

**原则**：花30分钟设计数据模型，比花30小时修改代码更值得。

我会帮你：

1. **识别核心对象**：系统里最重要的"一件事"是什么？
   - 例：会议纪要、销售线索、项目任务、用户反馈

2. **列举属性**：这个对象有哪些属性？
   - 删掉80%不必要的，只保留"在界面显示+会被查询筛选"的

3. **识别子对象**：有没有"一对多"的关系？
   - 例：会议纪要（父）→ 行动项（子）

4. **生成SQL**：我会给你建表语句

示例SQL模板：

```sql
-- 主表
CREATE TABLE your_entity (
  id TEXT PRIMARY KEY DEFAULT gen_random_uuid(),
  title TEXT NOT NULL,
  content TEXT,
  status TEXT DEFAULT 'active',
  tags JSONB DEFAULT '[]',
  meta JSONB DEFAULT '{}',
  created_by TEXT,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- 子表
CREATE TABLE your_sub_item (
  id TEXT PRIMARY KEY DEFAULT gen_random_uuid(),
  parent_id TEXT REFERENCES your_entity(id) ON DELETE CASCADE,
  text TEXT NOT NULL,
  owner TEXT,
  due_date DATE,
  status TEXT DEFAULT 'open',
  created_at TIMESTAMP DEFAULT NOW()
);

-- 索引
CREATE INDEX idx_parent ON your_sub_item(parent_id);
CREATE INDEX idx_status ON your_entity(status);
```

---

## 第三阶段：快速实现（3-6小时）

### Step 1：生成完整代码

基于你的需求和数据模型，我会生成一个**单HTML文件**，包含：

- ✅ 完整的前端界面（React组件）
- ✅ 本地存储逻辑（localStorage或Supabase连接）
- ✅ 响应式设计（手机和电脑都能用）
- ✅ AI集成代码（如需要）
- ✅ 错误处理和加载状态

你可以立即在浏览器里打开测试。

### Step 2：配置后端（如需要）

如果需要Supabase：

1. 打开 https://supabase.com
2. 创建新Project（免费）
3. 复制URL和Anon Key
4. 我会告诉你在HTML代码里粘贴哪里
5. 在Supabase的SQL Editor里执行建表语句

### Step 3：配置AI（如需要）

如果需要AI能力：

**获取API Key**：
- 通义千问：https://dashscope.console.aliyun.com/apiKey （国内推荐）
- DeepSeek：https://platform.deepseek.com/api_keys （文本处理推荐）
- Gemini：https://aistudio.google.com/app/apikey （需梯子）

**存储Key**：
- 小项目：直接存在HTML的localStorage里（不用上云）
- 中型项目：存在Supabase Edge Function的环境变量里（前端不暴露Key）

我会给你详细的代码模板和步骤。

### Step 4：本地调试（四阶段测试）

你在浏览器里测试这4个阶段：

```
□ Phase 1：UI能正常显示？响应式正常？
  按F12，看有没有JavaScript报错
  
□ Phase 2：本地存储能读写？
  添加数据，刷新页面，数据还在吗？
  
□ Phase 3：Supabase能连接？数据能读写？
  看Network标签，API请求有返回数据吗？
  
□ Phase 4：AI接口能调用？结果正确吗？
  调用AI，看返回的数据格式对吗？
```

如果遇到问题，给我Console的红色错误信息，我帮你快速修复。

---

## 第四阶段：上线部署（30分钟）

### 推荐方案：Vercel（最简单）

```
1. 打开 https://vercel.com
2. 登录（用GitHub账号最快）
3. 点 "Add New Project" → "Upload"
4. 把你的 index.html 文件拖上去
5. 等待部署完成
6. 获得一个公网URL（格式：https://xxx.vercel.app）

完成！你的应用现在在线了。
```

### 其他部署方案

| 方案 | 时间 | 特点 | 适合 |
|------|------|------|------|
| **Vercel** | 5分钟 | 全球CDN，国内可访问 | 推荐首选 |
| **Netlify** | 3分钟 | 拖拽最简单 | 个人项目 |
| **GitHub Pages** | 2分钟 | 完全免费 | 开源项目 |
| **阿里云OSS** | 15分钟 | 国内最快 | 国内用户为主 |

---

## 常见项目模式（拿来即用）

### 模式1：会议纪要系统（2-3天）
```
痛点：纸质记录难追踪
功能：记录会议 → AI提取待办 → 人工确认 → 保存
数据：meetings表 + action_items子表
AI：通义千问VL（OCR识别）或 DeepSeek（文本提取）
成本：0-5元（AI调用费，免费额度可能够）
```

### 模式2：销售CRM（3-5天）
```
痛点：客户信息散落在微信/Excel
功能：添加客户 → 跟进记录 → 机会分析
数据：customers表 + follow_ups子表
AI：可选（AI自动分析热门客户）
成本：0元
```

### 模式3：项目任务看板（1-2天）
```
痛点：任务没有统一视图
功能：添加任务 → 拖拽更新状态
数据：tasks表（title, status, priority, due_date）
AI：不需要
成本：0元
```

### 模式4：个人效率工具（1天）
```
痛点：自己的数据分散
功能：快速记录 + 本地查询
数据：本地localStorage
AI：可选
成本：0元
```

---

## AI工作流设计（如需要AI）

### 标准流程

```
【输入层】用户上传或输入
    ↓
【预处理】检测格式（图片？文字？PDF？）
    ↓
【AI提取】调用AI API → 返回结构化JSON
    ↓
【人工确认】展示给用户，允许修改（关键！不要完全依赖AI）
    ↓
【保存】写入数据库
    ↓
【展示】更新界面
```

### Prompt工程（如何让AI返回你想要的格式）

```
关键原则：

1. 角色设定
   "你是一个专业的[领域]信息提取助手"

2. 格式约束（最重要）
   "请严格按照以下JSON格式返回，不要包含任何其他文字"
   然后给出schema

3. 少样本示例
   "例如，输入'明天下午3点小明负责写报告'，
    输出：{"text": "写报告", "owner": "小明", "due": "2024-XX-XX"}"

4. 容错处理
   "如果无法确定某个字段，请填null，不要猜测"
```

---

## API Key安全存储

### 小项目（1-5人内部用）
```javascript
// 直接存localStorage，不上云
const storage = localStorage;
storage.setItem('api_key', 'sk-xxxxx');
const key = storage.getItem('api_key');
```

### 中型项目（有多用户）
```
Key存在Supabase Edge Function的Secret环境变量里
前端永远不拿到Key，只调用你的Edge Function接口
```

### 对外SaaS
```
有自己的后端服务器
Key统一管理，用户付费后获取调用额度
```

---

## 常见错误快速修复

| 错误现象 | 原因 | 解决方法 |
|---------|------|---------|
| 白屏/空白 | JS报错阻断了渲染 | 按F12看Console红色错误 |
| localStorage返回null | file://协议限制 | 用memStorage（见上方代码） |
| CORS error | 跨域限制 | 确认Supabase已设置RLS策略 |
| AI请求返回403 | API Key错误或额度用完 | 检查Key，登录平台查余额 |
| AI请求返回429 | 请求太频繁 | 加setTimeout延迟1000ms |
| 手机显示错位 | 没有viewport meta标签 | 确认有 `<meta name="viewport">` |
| Supabase连接超时 | 网络或URL错误 | 检查URL格式，换网络测试 |

---

## 上线前检查清单

- [ ] 核心业务流程完整走通（从输入到输出）
- [ ] 数据能正确保存和读取
- [ ] AI接口调用成功，结果符合预期
- [ ] 错误情况有友好提示（不要让用户看报错堆栈）
- [ ] Chrome/Firefox/Safari都能正常使用
- [ ] 手机上显示正常（无横向滚动条）
- [ ] API Key没有硬编码在前端代码里
- [ ] Supabase已开启RLS策略
- [ ] 首页加载时间 < 3秒

---

## 与AI工具高效协作的提示词模板

### 初始需求描述

```
我需要搭建一个[系统名称]，用于[核心场景]。
主要用户是[用户描述]，他们目前的痛点是[痛点]。

核心功能（只要最重要的1-2个）：
1. [功能1]
2. [功能2]

技术要求：
- 单HTML文件
- 使用React（CDN版本）
- 后端用Supabase（URL: xxx, Key: xxx）
- 需要调用[AI名称] API处理[具体任务]
- 手机和电脑都能用
- UI风格：[企业商务/科技/极简]

数据模型：
- 主表：[表名]，字段：[字段列表]
- 子表：[子表名]，字段：[字段列表]

请先确认你理解了需求，然后生成完整代码。
```

### 遇到问题时

```
【问题描述】点击[按钮名]后，期望[结果]但实际[实际结果]
【错误信息】[Console红色错误文字或截图]
【代码位置】大约在[函数名]附近
请只修改有问题的部分，保留其他代码不变。
```

### 要求扩展功能时

```
现在需要添加[新功能]：
- 触发时机：[什么时候触发]
- 输入：[用户操作什么]
- 处理：[需要做什么]
- 输出：[界面如何变化]
请在现有代码基础上添加，不要修改已有功能。
```

---

## 核心总结：从0到1的通用路径

```
1. 【想清楚】用三问法定义痛点和MVP（30分钟）
   ↓
2. 【设计数据】画出数据模型（10分钟）
   ↓
3. 【选技术栈】根据用户量和AI需求选技术（10分钟）
   ↓
4. 【生成框架】用本Skill的模板+Claude生成初始代码（30分钟）
   ↓
5. 【配置后端】Supabase建表（15分钟）+ 如需AI则配置Key（15分钟）
   ↓
6. 【本地调试】按四阶段测试，遇到问题截图给Claude修（1-3小时）
   ↓
7. 【用户测试】给真实用户试用，记录反馈（1天）
   ↓
8. 【上线部署】Vercel一键部署（15分钟）
   ↓
9. 【持续迭代】每周1-2个小功能更新（持续）
```

---

## 记住这句话

> **"The best code is no code at all. The second best is simple code you understand completely."**
> 最好的代码是没有代码。次好的是你完全理解的简单代码。

> **"先让它能用，再让它好用，最后才让它快。"**
> Make it work. Make it right. Make it fast.

你的任务是"想清楚需求"。AI的任务是"快速实现"。完美配合。

---

## 费用预估

### 第一个月（完全免费）
```
✅ Vercel部署：完全免费
✅ Supabase：500MB存储免费
✅ React CDN：完全免费
✅ Claude API：免费额度足够初期
✅ DeepSeek/通义千问：有免费额度

总成本：¥0
```

### 有付费用户后
```
用户付费 → 覆盖服务器成本
一般不需要你额外花钱
```

---

## 你的下一步

1. **用痛点三问**描述你的想法
2. **我会确认需求**和信息收集
3. **我给出技术方案**（技术栈+数据模型）
4. **我生成完整代码**（一个HTML文件）
5. **你本地测试**，遇到问题给我错误信息
6. **我快速修复**
7. **你部署到Vercel**（3分钟）
8. **完成**——你的应用在网上了

---

**准备好了吗？告诉我你的想法吧！**
