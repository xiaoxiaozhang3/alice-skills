# Trigger Cases

Use these cases to check whether skills trigger at the right time.

## Should Trigger

| Prompt               | Expected Skill                              |
| -------------------- | ------------------------------------------- |
| "帮我做一个新功能，但我还没想清楚细节" | to-prd or create-prd                        |
| "根据这个需求写一个实现方案"      | spec-driven-development or planning-and-task-breakdown |
| "继续上次那个任务"           | workflows/checkpoint-resume.md              |
| "这个测试失败了，帮我看看"       | diagnose or debugging-and-error-recovery    |
| "这个改完了吗"             | code-review-and-quality plus workflows/completion-gates.md |
| "前端要调用这个后端接口"        | planning-and-task-breakdown schema-first gate |

## Should Not Trigger Heavy Flow

| Prompt | Expected Behavior |
|---|---|
| "改一个错别字" | Direct edit and minimal verification |
| "解释这个文件是干嘛的" | Read and explain; no change folder unless user asks |
| "列一下目录" | Direct command; no skill workflow |
