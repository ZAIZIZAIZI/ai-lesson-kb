# AI 主课知识宝典（多日版）

手机端每日课堂复习工具：教案 + 选择/判断练习，答错可回看课堂时间码与原话。

## 在线访问

https://zaizizaizi.github.io/ai-lesson-kb/

## 当前课程

| 日 | 日期 | 主题 |
|----|------|------|
| Day 1 | 2026-07-15 | 先懂原理再选工具（应用/模型、幻觉、上下文、Skill/Agent） |
| Day 2 | 2026-07-16 | 会做工具·会说需求（Vibe Coding、Workflow、计划模式、多轮验收） |

顶部下拉可切换课程日；每日本地进度独立保存。

## 学员怎么用

1. 顶部选当天课程  
2. **学**：看教案（含课堂原话 vs 更严谨）  
3. **练**：模块测 / 综合练 / 错题重练  
4. **回看**：答错后对照时间码回忆场景  

## 老师每日如何更新（架构）

本地仓库（工作区）：

```
learn/
  build_kb.py      # 课程数据 + 页面构建脚本
  data.json        # 构建产物（课程 JSON）
  index.html       # 本地预览
learn-deploy/      # GitHub Pages 发布目录
  index.html
  README.md
minutes/<token>/transcript.txt   # 妙记逐字稿（只读素材）
```

**每日流程建议：**

1. 把飞书妙记链接给我（或自行 `lark-cli minutes +detail --transcript`）  
2. 在 `build_kb.py` 增加 `build_dayN()`：modules / cards / quotes / anchors / questions  
3. 在 `main()` 的 `courses` 列表 append 新日  
4. 运行：`python learn/build_kb.py`  
5. 推送 `learn-deploy` 到 GitHub：`git add -A && git commit && git push`  
6. Pages 约 1 分钟后更新，学员刷新即可看到新一天  

数据约定：

- 课程 id：`day1` / `day2` / …  
- 模块 id：`D1-M1`、`D2-M1` …（按日隔离）  
- 每题必须绑定 `review.anchorIds`（答错回看）  
- 进度 key：`localStorage ai-kb-v2`，按 `days[courseId]` 分日存储  

## 功能

- 多日课程切换 + 全日进度总览  
- 教案双栏对照（原话 / 严谨）  
- 选择 + 判断；答错回看金句/知识卡/时间码  
- 错题本；连续答对 2 次可移出  
- 零依赖单文件 HTML，手机优先  
