# AI 赋能自动控制原理课程实验

本仓库用于自动控制原理课程实验与报告整理，主要包含温度阶跃响应数据处理、一阶滞后模型辨识，以及基于智能优化算法的 PID 参数整定示例。

## 项目内容

- 使用实验温度数据拟合一阶惯性加纯滞后模型。
- 基于模型进行 PID 控制器设计与闭环响应仿真。
- 使用粒子群算法和遗传算法优化 PID 参数。
- 保存课程任务说明、实验报告、数据和结果图片。

## 目录结构

```text
.
+-- code/        # MATLAB 脚本
+-- data/        # 实验数据
+-- picture/     # 结果图片与参考图片
+-- 课程文档目录/  # 课程任务说明与实验报告
```

主要脚本：

- `code/fitting.m`：读取温度数据，平滑处理并辨识系统传递函数。
- `code/PID.m`：使用粒子群算法优化 PID 参数。
- `code/PID_GA.m`：使用遗传算法优化 PID 参数。

## 环境要求

建议使用 MATLAB 运行本项目。相关脚本依赖以下工具箱：

- Control System Toolbox
- Global Optimization Toolbox

## 运行方法

在仓库根目录下，可使用 MATLAB 批处理命令运行：

```powershell
matlab -batch "cd('data'); addpath('../code'); fitting"
matlab -batch "cd('code'); PID"
matlab -batch "cd('code'); PID_GA"
```

注意：`fitting.m` 默认从当前工作目录读取 `temperature.csv`，因此建议从 `data/` 目录运行，或在脚本中显式修改数据路径。

## 数据与结果

`data/temperature.csv` 保存温度响应数据。脚本运行后会输出模型参数、PID 参数和动态性能指标，并生成响应曲线图。相关截图或导出图可放入 `picture/` 目录。

## 贡献说明

提交代码前请至少运行受影响的 MATLAB 脚本，确认无报错并记录关键输出。更多贡献规范见 `AGENTS.md`。
