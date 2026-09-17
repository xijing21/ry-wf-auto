# 说明

本目录用于监控基础组件上游的代码变化动态，获取相应的动态和情报，结合 LLM 得出一些情报，辅助ruyi包管理器更新基础组件的版本

预计主要监控的基础组件有：
- GNU Toolchain
- LLVM
- QEMU

## 目录说明

```
ry-wf-auto/
├── README.md                              # 仓库总说明：任务清单、通用约定
├── .gitignore
├── .github/
│   └── workflows/                         # 所有任务的工作流统一放这里
│       ├── generate-summary.yml           # 已有：双周报卷首语生成
│       ├── gnu-upstream-track.yml         # 新增：GNU 上游动态监测
│       ├── llvm-upstream-track.yml        # 预留
│       └── qemu-upstream-track.yml        # 预留
│
└── upstream-tracker/                      # 新增：上游动态监测任务集
    ├── README.md                          # 本任务集总说明
    │
    ├── gnu-upstream/                      # GNU Toolchain 上游监测
    │   ├── README.md                      # 背景、需求、设计思路、使用方法
    │   ├── config/
    │   │   └── repos.yml                  # 监控仓库清单（gcc/binutils/glibc/gdb...）
    │   ├── scripts/
    │   │   ├── fetch_updates.py           # 拉取 commit / tag / release / PR
    │   │   ├── filter_important.py        # 关键词过滤（RISC-V 相关）
    │   │   └── gen_report.py              # 汇总生成结构化报告
    │   ├── prompts/
    │   │   └── analyze-updates.md         # LLM 分析提示词（判断重要进展）
    │   └── reports/                       # 输出的监测报告（按日期归档）
    │       └── .gitkeep
    │
    ├── llvm-upstream/                     # 预留
    │   └── README.md
    │
    └── qemu-upstream/                     # 预留
        └── README.md
```



## 需求

GNU 参考：https://github.com/xijing21/ruyisdk-work/edit/main/ai/gnu-news.md
