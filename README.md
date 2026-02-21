# Elastic Wave Dispersion in Nanowires

[English](#english-version) | [中文](#中文版)

## English Version

This project computes dimensionless dispersion relations of three elastic wave types in cylindrical nanowires:

- `Longitudinal.m`: Longitudinal waves
- `Torsional.m`: Torsional waves
- `Flexural.m`: Flexural waves

The implementation is based on Pochhammer-Kree-type dispersion equations. It uses Bessel functions and `fzero` for mode-by-mode root finding, and outputs `\xi-kR` and `\Omega-\omega R/c_T` dispersion curves.

### Publication

This repository contains the computational notebooks used in the publication below.
If you use this code or results, please cite:

[1]. Liu, S., Barinov, A. A., Yin, F. & Khvesyuk, V. I. Determination of thermal properties of unsmooth Si-nanowires. Chinese Phys. Lett. 41, 016301 (2024). https://cpl.iphy.ac.cn/article/10.1088/0256-307X/41/1/016301

### 1. Quick Start

In MATLAB, switch to this project directory and run any script:

```matlab
run('Torsional.m')
run('Longitudinal.m')
run('Flexural.m')
```

Each script computes one wave family and opens one dispersion figure.

### 2. Code Structure

- `Torsional.m`
  - Computes torsional eigen roots `betaX`
  - Builds dispersion relation `Omega = sqrt(beta^2 + xi^2)`
  - Plots multi-mode curves

- `Longitudinal.m`
  - Builds equations in real-root and imaginary-root regions
  - Tracks branches with `FindrealrootsL` and `FindimagerootsL`
  - Merges results and computes `OMEGAX = sqrt(alpha^2 + xi^2)`, then scales by `S=cL/cT`

- `Flexural.m`
  - Builds the flexural equation `Phi`
  - Finds real roots first, then extends branches in the imaginary-root region with `Findimageroots`
  - Merges branches and plots dispersion curves

## 中文版

本项目用于计算圆柱纳米线中三类弹性波的无量纲色散关系：

- `Longitudinal.m`：纵向波
- `Torsional.m`：扭转波
- `Flexural.m`：弯曲波

实现基于 Pochhammer-Kree 类频散方程，使用 Bessel 函数与 `fzero` 进行逐模态寻根，输出 `\xi-kR` 与 `\Omega-\omega R/c_T` 色散曲线。

### 发表

本仓库为以下论文发表时使用的计算代码。
如果你使用了本仓库代码或结果，请引用：

[1]. Liu, S., Barinov, A. A., Yin, F. & Khvesyuk, V. I. Determination of thermal properties of unsmooth Si-nanowires. Chinese Phys. Lett. 41, 016301 (2024). https://cpl.iphy.ac.cn/article/10.1088/0256-307X/41/1/016301

### 1. 快速开始

在 MATLAB 中切换到本项目目录后，运行任一脚本：

```matlab
run('Torsional.m')
run('Longitudinal.m')
run('Flexural.m')
```

每个脚本会计算一种波型并弹出一张色散图。

### 2. 代码结构

- `Torsional.m`
  - 计算扭转波本征根 `betaX`
  - 构造色散关系 `Omega = sqrt(beta^2 + xi^2)`
  - 绘制多模态曲线

- `Longitudinal.m`
  - 在实根/虚根区域分别构造方程
  - 通过 `FindrealrootsL` 与 `FindimagerootsL` 跟踪分支
  - 合并后计算 `OMEGAX = sqrt(alpha^2 + xi^2)`，并按 `S=cL/cT` 缩放

- `Flexural.m`
  - 构造弯曲波方程 `Phi`
  - 先求实根，再通过 `Findimageroots` 在虚根区域延拓分支
  - 合并分支并绘制色散曲线
