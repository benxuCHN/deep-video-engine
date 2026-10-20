# 输出契约与续作

## 项目目录

在用户指定目录输出。没有指定时，选择当前工作区下可识别的项目目录；遵守宿主对 outputs 和临时文件的约定。不要把生产资料写入 Skill 源目录。

按实际完成阶段建立文件，不为整齐生成空文件：

| 文件 | 内容 |
| --- | --- |
| project.json | 当前参数、已完成阶段、下一步、文件路径、需解决缺口 |
| structure.md | ST／V 证据、共通叙事规律、迁移边界 |
| ideas.md | 原创候选和搜索词 |
| sources.md | 已读 F 来源及检索／访问状态 |
| claims.csv | claim_id,claim,fact_source_id,locator,status,decision |
| script-review.md | 带 P ID 的旁白、来源映射、原创检查、估时 |
| narration.txt | 无段号、无引用和制作指令的纯旁白 |
| visual-bible.md | 本项目统一视觉规则 |
| scenes.csv | 逐镜表，使用标准 CSV 库写入，正确处理逗号和换行 |
| flow-batch-01.txt 等 | 可粘贴批次，各镜提示词独立完整 |
| edit-handoff.md | 配音、图层、音乐与剪辑说明，实测和估时分开 |

## 状态模型

project.json 至少记录 project_id、parameters、stage_status、artifacts、open_questions。parameters 包括 topic、audience、platform、language、duration_target、aspect_ratio、reference_sources、requested_stop。

阶段状态使用 not_started / in_progress / draft / complete / needs_input；镜头状态使用 planned / ready / submitted / generated / reviewed / failed。状态只能由真实证据推进，写好提示词不等于 submitted。

每个生成结果保留 scene_id、attempt、工具、实际设置、结果路径、审阅结果；若工具能提供作业 ID／费用，再记录它们，不猜测。失败不重排其他镜号，不重复提交已成功镜头。

## 续作

读 project.json 和用户本次提及的文件。确认新增材料和改动位置。修改主题或关键事实可能使旁白和分镜失效；只修改音乐不重写脚本。明确受影响阶段后更新产物，保留旧版本或可恢复记录。

最终告诉用户当前产物能用于什么、完成到哪一步、缺哪些材料。需要下一步时给一条带项目目录和阶段的可执行调用。
