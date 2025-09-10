---
description: 代码分析 + TDD策略规划
allowed-tools: [search_codebase, search_by_regex, view_files, list_dir, run_mcp]
argument-hint: 项目路径或分析重点
---

# 双Agent协作工作流

## 工作流概述
通过两个专业化Agent的协作，实现从代码理解到TDD策略制定的完整分析流程。

## Agent配置

### code-explorer (代码探索分析专家)
- **模型**: sonnet
- **工具**: search_codebase, search_by_regex, view_files, list_dir
- **职责**: 代码理解和分析，不编写代码

### strategic-planner (策略规划专家)
- **模型**: sonnet  
- **工具**: run_mcp, search_codebase, view_files
- **职责**: TDD策略规划和方案设计，不编写代码

## 阶段划分

### 阶段一：代码探索分析 (code-explorer)
**目标**: 深入理解项目结构和代码质量

**主要任务**:
1. **项目结构分析** - 使用 `search_codebase` 进行语义理解
2. **架构模式识别** - 使用 `list_dir` 了解项目结构
3. **关键组件分析** - 使用 `view_files` 深入分析关键文件
4. **代码质量评估** - 使用 `search_by_regex` 查找特定模式

### 阶段二：TDD策略规划 (strategic-planner)
**目标**: 基于代码分析制定测试驱动开发策略

**主要任务**:
1. **深度思考分析** - 使用 `run_mcp` (Sequential Thinking) 进行复杂问题分析
2. **TDD策略设计** - 制定测试驱动开发方案
3. **实施计划制定** - 规划分阶段执行步骤
4. **风险评估** - 识别潜在问题和应对措施

## 使用方式

### 基本语法
```
/workflow [项目路径或分析重点]
```

### 使用示例
```
/workflow src/components
/workflow 分析React组件架构并制定测试策略
/workflow 评估当前API设计的测试覆盖率
```

## 预期输出
1. **代码分析报告** - 项目结构、关键发现、改进建议
2. **TDD策略文档** - 测试方案、实施计划、成功指标
3. **优化建议** - 基于第一性原理的改进方向