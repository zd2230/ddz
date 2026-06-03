---
name: eplan-help
description: >
  EPLAN Platform 2026 Chinese (中文) complete help system reference — covers all 26 major topics including project editing, GED/graphical editor, schematics, connections, terminals/plugs, PLC, macros, project options, numbering, functions/devices, master data, reports/labels, translation, standards conversion, automation, Pro Panel, Fluid, Fluid Hose Configurator, Preplanning, and View.
  Use this skill whenever the user asks about EPLAN operations, how to do something in EPLAN, EPLAN platform functionality, EPLAN user guide, EPLAN help, EPLAN tutorial, EPLAN project management, EPLAN schematic editing, EPLAN connection editing, EPLAN terminal editing, EPLAN PLC editing, EPLAN macro usage, EPLAN numbering/DT, EPLAN reporting, EPLAN label printing, EPLAN translation, EPLAN Pro Panel, EPLAN Fluid, EPLAN Preplanning, or any EPLAN usage question in Chinese.
---

# EPLAN Platform 2026 — 完整帮助系统（中文）

本技能提供 EPLAN Platform 2026 的中文帮助系统完整参考。

> 源: https://www.eplan.help/zh-cn/Infoportal/Content/Plattform/2026/Content/htm/EPLAN_Help_k_start.htm

## 如何使用本技能

| 文件 | 内容 | 何时阅读 |
|------|------|----------|
| `references/platform-overview.md` | 平台概览、阅读提示、帮助系统使用 | 入门了解 |
| `references/project-management.md` | 编辑和管理项目、项目管理、项目结构 | 项目操作 |
| `references/pages.md` | 管理页：创建、编辑、导航 | 页操作 |
| `references/ged-graphics.md` | 图形编辑器(GED)使用 | 图形编辑 |
| `references/schematics.md` | 编辑原理图 | 画图 |
| `references/connections.md` | 编辑连接 | 连线操作 |
| `references/terminals-plugs.md` | 编辑端子和插头 | 端子/插头 |
| `references/plc.md` | 编辑 PLC 信息 | PLC 配置 |
| `references/macros.md` | 用宏工作 | 宏操作 |
| `references/project-options.md` | 使用项目选项 | 选项/变体 |
| `references/numbering.md` | 连接和设备的编号 | 编号/DT |
| `references/functions-devices.md` | 功能和设备的使用 | 功能/设备 |
| `references/project-data.md` | 管理项目数据 | 数据管理 |
| `references/master-data.md` | 管理主数据（符号/图框/表格/部件） | 主数据 |
| `references/messages.md` | 理解和管理消息 | 消息/检查 |
| `references/reports-labels.md` | 生成报表和输出标签 | 报表/标签 |
| `references/translation.md` | 生成自动翻译 | 翻译 |
| `references/standards-conversion.md` | 转换标准（IEC/NFPA/GB） | 标准转换 |
| `references/automation.md` | 项目操作自动化 | 自动化/脚本 |
| `references/propanel.md` | Eplan Pro Panel | 柜体设计 |
| `references/fluid.md` | Eplan Fluid | 液压/气动 |
| `references/fluid-hose.md` | Eplan Fluid Hose Configurator | 软管配置 |
| `references/preplanning.md` | Eplan Preplanning（预规划） | 预规划 |
| `references/view.md` | Eplan View | 查看/审阅 |
| `references/quick-ref.md` | 快速参考卡 | 速查 |

## EPLAN Platform 2026 架构

```
Eplan 平台
├── Eplan 平台 (主页)
│   ├── 阅读提示 (文档约定)
│   └── 使用帮助系统
├── Eplan 操作
│   ├── 用户界面
│   ├── 命令行
│   └── 基本操作
├── 编辑和管理项目 ★
│   ├── 项目对话框 (基础/内容/参考)
│   ├── 项目管理
│   ├── 项目结构 (结构标识符)
│   ├── 项目压缩/清除
│   ├── 数据备份
│   ├── 多用户操作/监控
│   ├── 外部编辑
│   ├── 项目审核/注释
│   ├── 工作区
│   └── 部分项目
├── 管理页 ★
├── 使用图形的编辑 (GED) ★
├── 编辑原理图 ★
├── 编辑连接 ★
├── 编辑端子和插头 ★
├── 编辑 PLC 信息 ★
├── 用宏工作 ★
├── 使用项目选项
├── 连接和设备的编号 (DT)
├── 功能和设备的使用 ★
├── 管理项目数据
├── 管理主数据 ★
├── 理解和管理消息 (检查运行)
├── 生成报表和输出标签 ★
├── 生成自动翻译
├── 转换标准
├── 项目操作自动化
├── Eplan Pro Panel ★
├── Eplan Fluid ★
├── Eplan Fluid Hose Configurator
├── Eplan Preplanning(预规划)
└── Eplan View
```

★ = 核心功能模块

## 关键术语速查

| 中文 | 英文/德文 | 说明 |
|------|-----------|------|
| 项目 | Project | 包含所有原理图页、主数据、报表的完整工程 |
| 页 | Page | 原理图/总览/报表的基本单位 |
| 图形编辑器 | GED (Graphical Editor) | 画图和编辑原理图的主界面 |
| 插入中心 | Insert Center | 快速插入符号、设备、宏的面板 |
| 宏 | Macro | 可重复使用的电路片段 |
| 结构标识符 | Structure Identifier | 高层代号/位置代号/文档类型等层级 |
| DT | Device Tag | 设备标识符（编号） |
| 连接定义点 | Connection Definition Point | 定义连接属性的符号 |
| 端子排 | Terminal Strip | 端子排管理 |
| PLC | Programmable Logic Controller | 可编程控制器 |
| 报表 | Report/Evaluation | 物料清单、端子图表、电缆图表等 |
| 主数据 | Master Data | 符号库、图框、表格、部件数据库 |
| 基本项目 | Basic Project | 模板项目 |
| 工作区 | Workspace | 用户界面布局配置 |
| 项目选项 | Project Option | 项目变体管理 |
| 检查运行 | Check Run | 项目电气逻辑验证 |
| 标准转换 | Standards Conversion | IEC ↔ NFPA ↔ GB 切换 |
| Pro Panel | Pro Panel | 3D 柜体设计与布线 |
| Fluid | Fluid | 液压/气动原理图设计 |
| Preplanning | Preplanning | 预规划（P&ID, 工艺流程图）|

## EPLAN 核心操作流程

### 典型工作流程
1. **创建项目** → 选择基本项目模板 → 设置结构标识符
2. **创建页** → 选择页类型（多线原理图/总览/...）
3. **插入符号/设备** → 使用插入中心或直接拖拽
4. **自动/手动连线** → 生成连接
5. **编号** → 设备编号(DT) + 连接编号
6. **检查运行** → 发现并修复电气逻辑错误
7. **生成报表** → 物料清单、端子图表、电缆图表
8. **导出/打印** → PDF、DXF、标签打印
9. **备份** → 项目备份到磁盘

## 参考文件的加载策略

- **快速查找**：先读 `references/quick-ref.md`
- **项目操作问题**：读 `references/project-management.md`
- **画图/编辑问题**：读 `references/schematics.md` + `references/ged-graphics.md`
- **报表/标签**：读 `references/reports-labels.md`
- **3D 柜体**：读 `references/propanel.md`
- **液压气动**：读 `references/fluid.md`
