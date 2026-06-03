# EPLAN Platform 2026 — Pro Panel、Fluid、Preplanning、View

## Eplan Pro Panel

Pro Panel 是 EPLAN 的 3D 柜体设计和布线模块。

### 核心功能
- **3D 柜体布局** — 在 3D 空间中放置导轨、线槽、安装板
- **设备布局** — 在安装板上放置电气元件（断路器、继电器、端子等）
- **3D 宏** — 使用 3D 组件宏，包含精确的几何尺寸
- **布线路径** — 自动计算导线/电缆在柜内的走线路径
- **线槽填充率** — 计算线槽/导管的填充率
- **钻孔/攻丝** — 自动生成安装孔、钻孔和攻丝数据
- **NC 数据导出** — 导出加工数据给 CNC 设备
- **制造数据导出** — 导出给 Rittal 等配套设备的加工数据

### 典型工作流
1. 创建安装板布局空间
2. 放置 3D 组件（从 Data Portal 或部件库）
3. 设置布线路径
4. 执行自动布线
5. 生成制造数据（钻孔、攻丝、切割）
6. 生成 3D 可视化和文档

### 相关 Actions
- `XAMlExportProductionData2RASCenterAction` — 导出给 Rittal RiPanel Processing Center
- `XAMlExportProductionData2SmartMountingAction` — 导出给 Rittal RiPanel

## Eplan Fluid

Fluid 是 EPLAN 的液压和气动原理图设计模块。

### 核心功能
- **液压原理图设计** — 绘制液压回路图
- **气动原理图设计** — 绘制气动回路图
- **流体符号库** — 泵、阀、缸、过滤器、蓄能器等
- **管道/软管设计** — 定义管道属性和连接
- **流体报表** — 液压元件清单、管道列表

### 特有概念
- **流体功能** — 液压/气动元件的功能定义
- **管道连接** — 液压管路的连接点
- **流体端子** — 液压/气动端子排
- **执行器/传感器** — 液压缸、气动缸、压力开关等

### 集成
- 可与电气原理图共享项目数据库
- 流体元件与电气元件的交叉引用
- 统一的部件数据库

## Eplan Fluid Hose Configurator

- 软管配置专用工具
- 自动计算软管长度和弯曲半径
- 支持多种软管品牌和型号
- 与 Fluid 原理图双向同步

## Eplan Preplanning (预规划)

Preplanning 是 EPLAN 的工艺预规划模块。

### 核心功能
- **P&ID (Piping & Instrumentation Diagram)** — 管道仪表流程图
- **工艺流程图** — 流程工业的预设计
- **规划对象 (Planning Object)** — 代表工艺设备/功能
- **细节工程** — 从预规划导出到详细设计
- **段模板 (Segment Template)** — 预定义工艺段模板

### 相关 Actions
- `ImportPrePlanningData` — 导入预规划数据
- `ExportSegmentsTemplate` / `ImportSegmentsTemplate` — 段模板导入导出
- `XPlaUpdateDetailAction` — 更新规划对象的详细工程

## Eplan View

- 项目查看/审阅工具
- 不需要 EPLAN 许可证即可查看项目
- 支持查看原理图、报表、3D 布局
- 可用于客户审阅和现场查看
