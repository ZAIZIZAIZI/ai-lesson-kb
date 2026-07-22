# AI 主课知识宝典（多日版）

手机端每日课堂复习工具：教案 + 选择/判断练习，答错可回看课堂时间码与原话。

## 在线访问

https://zaizizaizi.github.io/ai-lesson-kb/

## 当前课程

| 日 | 日期 | 主题 | 题量 |
|----|------|------|------|
| Day 1 | 2026-07-15 | 先懂原理再选工具（应用/模型、幻觉、上下文、Skill/Agent） | 16 |
| Day 2 | 2026-07-16 | 会做工具·会说需求（Vibe Coding、Workflow、计划模式） | 18 |
| Day 3 | 2026-07-22 | 提示词专项（无歧义、角色扮演、调用工具、结构化/Markdown） | 20 |

顶部下拉可切换课程日；每日本地进度独立保存。

## 学员怎么用

1. 顶部选当天课程  
2. **学**：看教案（含课堂原话 vs 更严谨）  
3. **练**：模块测 / 综合练 / 错题重练  
4. **回看**：答错后对照时间码回忆场景  

## 老师每日如何更新

本地：

```
learn/build_kb.py   # 加 build_dayN() 后构建
learn/index.html
learn-deploy/       # 推 GitHub Pages
```

流程：

1. 发飞书妙记链接  
2. 在 `build_kb.py` 增加 `build_dayN` 并加入 `courses`  
3. `python learn/build_kb.py`  
4. `cd learn-deploy && git add -A && git commit && git push`  

进度 key：`localStorage ai-kb-v2` → `days[courseId]`
