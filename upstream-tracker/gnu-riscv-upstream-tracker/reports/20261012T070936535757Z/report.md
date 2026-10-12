# GNU RISC-V 上游更新报告

统计窗口（UTC）：2026-10-07T06:51:00Z 至 2026-10-12T07:09:36Z
生成时间（UTC）：2026-10-12T07:09:36Z

共 15 条相关更新：高 3、中 10、低 2。

优先级和打包候选由规则决定；LLM 辅助分析仅供参考，最终打包需人工评估和构建测试。
提交已合入不代表已经发布；关联 PR 的状态单独列出。

## 仓库采集状态

- RTEMS/sourceware-mirror-binutils-gdb：ok；分支 master
  采集窗口（UTC）：2026-10-07T06:51:00Z 至 2026-10-12T07:09:36Z
- gcc-mirror/gcc：ok；分支 master
  采集窗口（UTC）：2026-10-07T06:51:00Z 至 2026-10-12T07:09:36Z
- sailfishos-mirror/glibc：ok；分支 master
  采集窗口（UTC）：2026-10-07T06:51:00Z 至 2026-10-12T07:09:36Z

## 采集警告

- RTEMS/sourceware-mirror-binutils-gdb：轻量标签没有独立时间，只能用所指提交的时间代替。
- gcc-mirror/gcc：轻量标签没有独立时间，只能用所指提交的时间代替。
- 分页在第 1 页停止，元数据覆盖不完整。

## 高优先级

### \[RISC-V\] Remove obsolete, never taken to silicon xventanacondops extension

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-11T18:32:31Z
- 作者：JeffreyALaw；SHA：06cee27b6943fdfe6082dbee4c260b2efe22a193
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/06cee27b6943fdfe6082dbee4c260b2efe22a193)
- 规则判断：high / compiler-option；打包候选：是，待人工评估
- 命中规则：functional:support、keyword:compiler-option:options、keyword:isa-extension:extension、keyword:isa-extension:zicond、path:gcc/config/riscv/predicates.md、path:gcc/config/riscv/riscv-ext-ventana.def、path:gcc/config/riscv/riscv-ext.def、path:gcc/config/riscv/riscv-ext.opt、path:gcc/config/riscv/riscv-opts.h、path:gcc/config/riscv/riscv.cc、path:gcc/config/riscv/riscv.md、path:gcc/config/riscv/t-riscv、path:gcc/config/riscv/zicond.md、path:gcc/doc/riscv-ext.texi、path:gcc/testsuite/gcc.target/riscv/cset-sext-ventana-rtl.c、path:gcc/testsuite/gcc.target/riscv/cset-sext-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibfeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibfge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibfgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibfle-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibflt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibfne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibgeu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibgtu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdible-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibleu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdiblt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibltu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdibne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdieq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdifeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdifge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdifgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdifle-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdiflt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdifne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdige-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdigeu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdigt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdigtu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdile-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdileu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdilt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdiltu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movdine-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibfeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibfge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibfgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibfle-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibflt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibfne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibgeu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibgtu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsible-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibleu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsiblt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibltu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsibne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsieq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsifeq-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsifge-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsifgt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsifle-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsiflt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsifne-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsige-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsigeu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsigt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsigtu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsile-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsileu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsilt-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsiltu-ventana.c、path:gcc/testsuite/gcc.target/riscv/movsine-ventana.c、path:gcc/testsuite/gcc.target/riscv/pr116240.c、path:gcc/testsuite/gcc.target/riscv/predef-30.c、path:gcc/testsuite/gcc.target/riscv/ventana-16122.c、path:gcc/testsuite/gcc.target/riscv/xventanacondops-primitiveSemantics-rv32.c、path:gcc/testsuite/gcc.target/riscv/xventanacondops-primitiveSemantics.c、path:gcc/testsuite/gcc.target/riscv/xventanacondops-xor-01.c、token:risc-v、token:riscv、token:rv32
- 涉及文件：gcc/config/riscv/predicates.md、gcc/config/riscv/riscv-ext-ventana.def、gcc/config/riscv/riscv-ext.def、gcc/config/riscv/riscv-ext.opt、gcc/config/riscv/riscv-opts.h、gcc/config/riscv/riscv.cc、gcc/config/riscv/riscv.md、gcc/config/riscv/t-riscv、gcc/config/riscv/zicond.md、gcc/doc/riscv-ext.texi、gcc/testsuite/gcc.target/riscv/cset-sext-ventana-rtl.c、gcc/testsuite/gcc.target/riscv/cset-sext-ventana.c、gcc/testsuite/gcc.target/riscv/movdibeq-ventana.c、gcc/testsuite/gcc.target/riscv/movdibfeq-ventana.c、gcc/testsuite/gcc.target/riscv/movdibfge-ventana.c、gcc/testsuite/gcc.target/riscv/movdibfgt-ventana.c、gcc/testsuite/gcc.target/riscv/movdibfle-ventana.c、gcc/testsuite/gcc.target/riscv/movdibflt-ventana.c、gcc/testsuite/gcc.target/riscv/movdibfne-ventana.c、gcc/testsuite/gcc.target/riscv/movdibge-ventana.c、gcc/testsuite/gcc.target/riscv/movdibgeu-ventana.c、gcc/testsuite/gcc.target/riscv/movdibgt-ventana.c、gcc/testsuite/gcc.target/riscv/movdibgtu-ventana.c、gcc/testsuite/gcc.target/riscv/movdible-ventana.c、gcc/testsuite/gcc.target/riscv/movdibleu-ventana.c、gcc/testsuite/gcc.target/riscv/movdiblt-ventana.c、gcc/testsuite/gcc.target/riscv/movdibltu-ventana.c、gcc/testsuite/gcc.target/riscv/movdibne-ventana.c、gcc/testsuite/gcc.target/riscv/movdieq-ventana.c、gcc/testsuite/gcc.target/riscv/movdifeq-ventana.c、gcc/testsuite/gcc.target/riscv/movdifge-ventana.c、gcc/testsuite/gcc.target/riscv/movdifgt-ventana.c、gcc/testsuite/gcc.target/riscv/movdifle-ventana.c、gcc/testsuite/gcc.target/riscv/movdiflt-ventana.c、gcc/testsuite/gcc.target/riscv/movdifne-ventana.c、gcc/testsuite/gcc.target/riscv/movdige-ventana.c、gcc/testsuite/gcc.target/riscv/movdigeu-ventana.c、gcc/testsuite/gcc.target/riscv/movdigt-ventana.c、gcc/testsuite/gcc.target/riscv/movdigtu-ventana.c、gcc/testsuite/gcc.target/riscv/movdile-ventana.c、gcc/testsuite/gcc.target/riscv/movdileu-ventana.c、gcc/testsuite/gcc.target/riscv/movdilt-ventana.c、gcc/testsuite/gcc.target/riscv/movdiltu-ventana.c、gcc/testsuite/gcc.target/riscv/movdine-ventana.c、gcc/testsuite/gcc.target/riscv/movsibeq-ventana.c、gcc/testsuite/gcc.target/riscv/movsibfeq-ventana.c、gcc/testsuite/gcc.target/riscv/movsibfge-ventana.c、gcc/testsuite/gcc.target/riscv/movsibfgt-ventana.c、gcc/testsuite/gcc.target/riscv/movsibfle-ventana.c、gcc/testsuite/gcc.target/riscv/movsibflt-ventana.c、gcc/testsuite/gcc.target/riscv/movsibfne-ventana.c、gcc/testsuite/gcc.target/riscv/movsibge-ventana.c、gcc/testsuite/gcc.target/riscv/movsibgeu-ventana.c、gcc/testsuite/gcc.target/riscv/movsibgt-ventana.c、gcc/testsuite/gcc.target/riscv/movsibgtu-ventana.c、gcc/testsuite/gcc.target/riscv/movsible-ventana.c、gcc/testsuite/gcc.target/riscv/movsibleu-ventana.c、gcc/testsuite/gcc.target/riscv/movsiblt-ventana.c、gcc/testsuite/gcc.target/riscv/movsibltu-ventana.c、gcc/testsuite/gcc.target/riscv/movsibne-ventana.c、gcc/testsuite/gcc.target/riscv/movsieq-ventana.c、gcc/testsuite/gcc.target/riscv/movsifeq-ventana.c、gcc/testsuite/gcc.target/riscv/movsifge-ventana.c、gcc/testsuite/gcc.target/riscv/movsifgt-ventana.c、gcc/testsuite/gcc.target/riscv/movsifle-ventana.c、gcc/testsuite/gcc.target/riscv/movsiflt-ventana.c、gcc/testsuite/gcc.target/riscv/movsifne-ventana.c、gcc/testsuite/gcc.target/riscv/movsige-ventana.c、gcc/testsuite/gcc.target/riscv/movsigeu-ventana.c、gcc/testsuite/gcc.target/riscv/movsigt-ventana.c、gcc/testsuite/gcc.target/riscv/movsigtu-ventana.c、gcc/testsuite/gcc.target/riscv/movsile-ventana.c、gcc/testsuite/gcc.target/riscv/movsileu-ventana.c、gcc/testsuite/gcc.target/riscv/movsilt-ventana.c、gcc/testsuite/gcc.target/riscv/movsiltu-ventana.c、gcc/testsuite/gcc.target/riscv/movsine-ventana.c、gcc/testsuite/gcc.target/riscv/pr116240.c、gcc/testsuite/gcc.target/riscv/predef-30.c、gcc/testsuite/gcc.target/riscv/ventana-16122.c、gcc/testsuite/gcc.target/riscv/xventanacondops-primitiveSemantics-rv32.c、gcc/testsuite/gcc.target/riscv/xventanacondops-primitiveSemantics.c、gcc/testsuite/gcc.target/riscv/xventanacondops-xor-01.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / compiler-option（不改变规则判断）
- 中文摘要：GCC 移除从未流片的 RISC-V xventanacondops 扩展支持，相关条件移动逻辑改为只使用标准化的 zicond，并删除对应扩展描述文件、选项和文档。
- 影响：该提交会影响 RISC-V 后端编译选项和扩展识别：使用旧 xventanacondops 选项的用户将不再被接受，条件移动相关代码路径改为依赖 zicond。由于仅看到上游提交，尚未确认对应 GCC 版本、构建测试结果以及 RuyiSDK 是否已同步合入，实际影响需要人工核对。
- 打包建议：请人工核对该提交是否已合入 RuyiSDK 所用 GCC 分支或发布版本，评估移除旧扩展选项对现有用户和文档的兼容影响；重点确认 zicond 路径在目标 RISC-V 配置下功能正常，并运行 rv32/rv64 相关回归测试后再决定打包更新。

### RISC-V: Add -z zicfilp=, -z zicfiss= and the CFI report options

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:51:12Z
- 作者：kito-cheng；SHA：5c624ad4aa3cc5290da28a5c5bcd6bae51b7b0f5
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/5c624ad4aa3cc5290da28a5c5bcd6bae51b7b0f5)
- 规则判断：high / compiler-option；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:compiler-option:options、keyword:isa-extension:zicfilp、keyword:isa-extension:zicfiss、path:bfd/elfnn-riscv.c、path:bfd/elfxx-riscv.h、path:ld/emultempl/riscvelf.em、path:ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、path:ld/testsuite/ld-riscv-elf/property-cfi-never.d、path:ld/testsuite/ld-riscv-elf/property-zicfilp-bad.d、path:ld/testsuite/ld-riscv-elf/property-zicfilp-never.d、path:ld/testsuite/ld-riscv-elf/property-zicfilp-unlabeled-report-single.d、path:ld/testsuite/ld-riscv-elf/property-zicfilp-unlabeled-report.d、path:ld/testsuite/ld-riscv-elf/property-zicfiss-never.d、path:ld/testsuite/ld-riscv-elf/property-zicfiss-report-error.d、path:ld/testsuite/ld-riscv-elf/property-zicfiss-report.d、path:ld/testsuite/ld-riscv-elf/zicfilp-force-plt.d、path:ld/testsuite/ld-riscv-elf/zicfilp-force-plt.s、path:ld/testsuite/ld-riscv-elf/zicfilp-never-plt.d、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c、bfd/elfxx-riscv.h、ld/NEWS、ld/emultempl/riscvelf.em、ld/ld.texi、ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、ld/testsuite/ld-riscv-elf/property-cfi-never.d、ld/testsuite/ld-riscv-elf/property-zicfilp-bad.d、ld/testsuite/ld-riscv-elf/property-zicfilp-never.d、ld/testsuite/ld-riscv-elf/property-zicfilp-unlabeled-report-single.d、ld/testsuite/ld-riscv-elf/property-zicfilp-unlabeled-report.d、ld/testsuite/ld-riscv-elf/property-zicfiss-never.d、ld/testsuite/ld-riscv-elf/property-zicfiss-report-error.d、ld/testsuite/ld-riscv-elf/property-zicfiss-report.d、ld/testsuite/ld-riscv-elf/zicfilp-force-plt.d、ld/testsuite/ld-riscv-elf/zicfilp-force-plt.s、ld/testsuite/ld-riscv-elf/zicfilp-never-plt.d
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / compiler-option（不改变规则判断）
- 中文摘要：binutils-gdb 的 RISC-V 链接器新增 -z zicfilp=、-z zicfiss= 以及对应的 CFI 报告选项，用于按 RISC-V 工具链约定标记和报告 Zicfilp、Zicfiss GNU property。
- 影响：新增链接器选项会扩展 RISC-V 链接命令行能力和 GNU property 标记行为，可能影响控制流完整性相关工程流程。该提交只代表上游已合并，尚不能证明已进入 RuyiSDK 所用版本或已完成各目标平台测试，实际可用性需人工确认。
- 打包建议：请人工核对目标 binutils/gdb 版本是否包含此提交，评估 -z zicfilp/-z zicfiss 默认行为与现有链接脚本的兼容性；测试 implicit、unlabeled、always、never 及 report 选项组合，并关注与 lld 行为的一致性后再纳入打包。

### RISC-V: Name the missing extension for the MIPS vendor instructions

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:24:34Z
- 作者：kito-cheng；SHA：55c6fd1d3ac54ca36983d657e5692b6e9e412148
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/55c6fd1d3ac54ca36983d657e5692b6e9e412148)
- 规则判断：high / isa-extension；打包候选：是，待人工评估
- 命中规则：functional:add、functional:supports、keyword:isa-extension:extension、path:bfd/elfxx-riscv.c、path:gas/testsuite/gas/riscv/mips-insns-fail.d、path:gas/testsuite/gas/riscv/mips-insns-fail.l、path:gas/testsuite/gas/riscv/mips-insns-fail.s、token:risc-v、token:riscv
- 涉及文件：bfd/elfxx-riscv.c、gas/testsuite/gas/riscv/mips-insns-fail.d、gas/testsuite/gas/riscv/mips-insns-fail.l、gas/testsuite/gas/riscv/mips-insns-fail.s
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / isa-extension（不改变规则判断）
- 中文摘要：binutils-gdb 为 RISC-V 中四类 MIPS 厂商指令补齐扩展名映射，避免在缺少相应扩展时输出不可达的 INSN\_CLASS\_\* 内部错误，并新增对应诊断测试。
- 影响：该改动主要改进错误诊断，涉及 RISC-V 扩展识别和汇编器对 MIPS 厂商指令的处理。功能影响预计较小，但上游提交的测试和版本合入情况仍需人工核对，不能直接视为已发布支持。
- 打包建议：请核对目标 binutils/gdb 版本是否包含该提交，确认新的缺失扩展诊断测试通过；重点验证相关 MIPS 厂商指令在缺少扩展时的报错文本是否清晰，并随对应工具链版本更新评估是否纳入 RuyiSDK 打包。


## 中优先级

### \[RISC-V\] Fix remaining AOP related regressions on the RISC-V port

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-11T15:19:22Z
- 作者：Jeff Law；SHA：de2ea1f8b15f05264310a5e7c29328591c13de49
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/de2ea1f8b15f05264310a5e7c29328591c13de49)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、keyword:hardware:k3、keyword:isa-extension:zba、path:gcc/config/riscv/riscv.md、token:risc-v、token:riscv、token:rv32、token:rv64
- 涉及文件：gcc/config/riscv/riscv.md
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：GCC RISC-V 后端新增 aop&lt;mode&gt;3 expander，修复 AOP 决策在 PLUS 与 IOR 之间选择不当导致的剩余回归，涉及 ZBA、rv32、rv64 等配置。
- 影响：该提交旨在恢复正确代码生成，可能消除部分 RISC-V 测试失败和性能回退。当前仅凭上游提交信息无法确认目标 GCC 版本的构建与回归结果，也不能证明 RuyiSDK 已支持或合入，影响需结合实际包版本判断。
- 打包建议：请人工核对该修复是否位于 RuyiSDK 所用 GCC 分支，重点在 rv32/rv64、ZBA 及提交中提到的 k3/c920 等硬件配置上运行回归测试，确认 AOP 相关 pr80770-2、pr58727、pr93504 不再回退后再打包。

### \[RISC-V\] Fix pr58727 code quality regression on RISC-V

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-11T14:43:39Z
- 作者：Jeff Law；SHA：9613bdb1922e62e20da5a2893d27a9f6ef296afc
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/9613bdb1922e62e20da5a2893d27a9f6ef296afc)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、keyword:bugfix:regression、keyword:hardware:k3、path:gcc/config/riscv/bitmanip.md、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/bitmanip.md
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：GCC RISC-V 后端在 bitmanip.md 中增加新的 3-&gt;2 splitter，修复外层 IOR、内层 AND 与 PLUS 重写交互导致的 pr58727 代码质量回归。
- 影响：该改动针对 RISC-V 位操作优化路径，可改善特定模式下的指令序列生成。当前仅看到上游提交，尚未确认是否已进入目标 GCC 版本或通过 RuyiSDK 相关平台测试，影响范围和稳定性需人工验证。
- 打包建议：请人工核对提交在 RuyiSDK 所用 GCC 分支的合入状态，重点回归 RISC-V bitmanip 优化、c920/k3 平台以及 rv32/rv64 配置，确认不再出现 and+bclr+plus 等预期外序列后再纳入打包。

### xtensa: compare SEC\_MERGE literals by their merged addresses

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-09T11:03:43Z
- 作者：Lapshin；SHA：527a092ac82424791b15c6db14bfcdcfc56e052c
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/527a092ac82424791b15c6db14bfcdcfc56e052c)
- 规则判断：medium / other；打包候选：否
- 命中规则：token:risc-v
- 涉及文件：bfd/elf32-xtensa.c、ld/testsuite/ld-xtensa/coalesce-merge-1.s、ld/testsuite/ld-xtensa/coalesce-merge-2.s、ld/testsuite/ld-xtensa/coalesce-merge.d、ld/testsuite/ld-xtensa/coalesce-merge.t、ld/testsuite/ld-xtensa/xtensa.exp
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：Xtensa 链接器改为按合并后的地址比较 SEC\_MERGE 字面量，避免两个指向相同输入偏移但合并后地址不同的引用被错误合并为同一个字面量。
- 影响：该提交位于 Xtensa 后端，对 RISC-V 工具链的直接功能影响很小，但属于同一 binutils-gdb 仓库的链接器修改。由于来源是上游提交，未验证构建和测试，且规则未将其列为 RISC-V 打包候选，是否需要关注取决于整体 binutils 同步策略。
- 打包建议：请人工判断 RuyiSDK 是否整体同步该 binutils-gdb 仓库；该提交并非 RISC-V 特定改动，通常可不作为 RISC-V 打包重点。如随上游版本整体升级，建议保留原有 Xtensa 测试并关注通用链接器行为是否受影响。

### RISC-V: Suppress may be used uninitialized warning

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T13:56:53Z
- 作者：kito-cheng；SHA：079dc6f5083e3614d52c49de896f33a6c87d4e09
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/079dc6f5083e3614d52c49de896f33a6c87d4e09)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：binutils-gdb 的 RISC-V 链接器代码将局部变量 insn 初始化为 0，以消除可能未初始化警告。
- 影响：该改动属于编译告警清理，不改变链接器功能行为。当前仅能确认上游已合并该提交，无法证明已进入 RuyiSDK 所用版本，实际功能影响很低。
- 打包建议：请核对目标 binutils/gdb 版本是否包含此告警修复；风险较低，可随对应工具链版本更新。建议在构建时确认 elfnn-riscv.c 不再产生相关 -Wmaybe-uninitialized 告警即可。

### RISC-V: Introduce TLSDESC relaxation.

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T08:11:21Z
- 作者：ishitatsuyuki；SHA：2c4ccb8103d73917d769cf6c35fa8b71424f20ca
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/2c4ccb8103d73917d769cf6c35fa8b71424f20ca)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、path:bfd/elfxx-riscv.c、path:include/elf/riscv.h、path:ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、path:ld/testsuite/ld-riscv-elf/tlsbin.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-32-dyn.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-32-norelax.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-32.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-32.s、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-dyn.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie-norelax.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-ie.s、path:ld/testsuite/ld-riscv-elf/tlsdesc-le-norelax.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-le.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-le.s、path:ld/testsuite/ld-riscv-elf/tlsdesc-lib.s、path:ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed-le.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed-le.s、path:ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed.d、path:ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed.s、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c、bfd/elfxx-riscv.c、include/elf/riscv.h、ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、ld/testsuite/ld-riscv-elf/tlsbin.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie-32-dyn.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie-32-norelax.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie-32.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie-32.s、ld/testsuite/ld-riscv-elf/tlsdesc-ie-dyn.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie-norelax.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie.d、ld/testsuite/ld-riscv-elf/tlsdesc-ie.s、ld/testsuite/ld-riscv-elf/tlsdesc-le-norelax.d、ld/testsuite/ld-riscv-elf/tlsdesc-le.d、ld/testsuite/ld-riscv-elf/tlsdesc-le.s、ld/testsuite/ld-riscv-elf/tlsdesc-lib.s、ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed-le.d、ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed-le.s、ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed.d、ld/testsuite/ld-riscv-elf/tlsdesc-unrelaxed.s
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：binutils-gdb 为 RISC-V 引入 TLSDESC 松弛：在可执行文件中将 TLSDESC 访问转换为 IE 或本地符号的 LE，并支持在 RELAX 路径删除前两条指令，或在 no-relax 路径原地重写为等价序列。
- 影响：该功能新增会影响 RISC-V TLS 描述符的链接结果，尤其使静态可执行文件可能正确解析 TLSDESC。该提交仅表示上游已合并，尚未确认是否纳入 RuyiSDK 所用版本或通过 RV32/RV64、relax/no-relax 等测试。
- 打包建议：请人工评估是否需要在 RuyiSDK 中同步该 TLSDESC 支持；如需纳入，应核对 binutils/gdb 版本合入状态，并在 RV32/RV64 上测试静态与动态 TLS、relax 与 no-relax 场景，同时关注与 lld 行为及现有 TLS 用例的兼容性。

### RISC-V: Move STATIC\_TLS handling into record\_tls\_type.

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:59:49Z
- 作者：ishitatsuyuki；SHA：34ee5769160d92f958feb286dece925747a47719
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/34ee5769160d92f958feb286dece925747a47719)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：RISC-V binutils 的 BFD ELF 后端将 STATIC\_TLS 处理逻辑移入 riscv\_elf\_record\_tls\_type，新增 bfd\_link\_info 参数，并在 R\_RISCV\_TPREL\_HI20 分支补充缺失的提前返回。
- 影响：该提交修改 bfd/elfnn-riscv.c 的 TLS 类型记录流程，可能影响 RISC-V TLS 重定位检查行为。状态为已合入上游提交；元数据未提供测试结果，不能证明已通过构建或包含于正式发布。
- 打包建议：规则未判定为打包候选。建议仅在维护者需要跟进 RISC-V binutils TLS 相关修复时人工核对目标版本是否包含该提交，并评估对现有 TLS 用例的回归风险。

### RISC-V: Add elf\_link\_hash\_entry to relax\_func args.

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:59:49Z
- 作者：ishitatsuyuki；SHA：60b08e6b3adf81fbd95cc69511cac640714174e2
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/60b08e6b3adf81fbd95cc69511cac640714174e2)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：RISC-V binutils 的重定位松弛函数参数中新增 elf\_link\_hash\_entry，用于记录 PC-relative hi reloc 的哈希符号，并将相关辅助函数调用路径统一传递该参数。
- 影响：变更集中在 bfd/elfnn-riscv.c 的松弛逻辑，可能影响后续链接器松弛行为所需符号信息。该提交已合入上游但元数据未展示测试结果，不能视为已发布或已验证。
- 打包建议：规则未判定为打包候选。建议维护者在同步 RISC-V binutils 上游时人工确认该提交是否随目标版本合入，并关注链接器松弛相关用例是否受影响。

### RISC-V: Unify TLS handling in check\_relocs.

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:59:49Z
- 作者：ishitatsuyuki；SHA：701b5cda0b47af1db756addb8a5dc6c9710b0d9c
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/701b5cda0b47af1db756addb8a5dc6c9710b0d9c)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：RISC-V binutils 在 check\_relocs 中合并 TLS 重定位的 switch 分支，统一 GOT\_TLS\_IE/GOT\_TLS\_LE 相关通用检查路径，以配合 transition 引入后的多重定位类型映射。
- 影响：该提交调整 TLS 重定位检查结构，降低多路径重复但可能改变边界条件。已合入上游；构建和测试情况未知，需谨慎评估。
- 打包建议：规则未判定为打包候选。建议仅在需要持续跟进 RISC-V binutils TLS 实现时由维护者核对版本合入状态，并评估链接器 TLS 行为回归风险。

### RISC-V: Update the unlabeled landing pad PLT to the latest psABI

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:51:12Z
- 作者：kito-cheng；SHA：d3eea828943c60cfe135c2830a6e7a23e82b11e6
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/d3eea828943c60cfe135c2830a6e7a23e82b11e6)
- 规则判断：medium / profile-abi；打包候选：是，待人工评估
- 命中规则：keyword:isa-extension:zicfilp、keyword:profile-abi:psabi、path:bfd/elfnn-riscv.c、path:ld/testsuite/ld-riscv-elf/zicfilp-unlabeled-plt.d、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c、ld/testsuite/ld-riscv-elf/zicfilp-unlabeled-plt.d
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / profile-abi（不改变规则判断）
- 中文摘要：按最新 RISC-V psABI 更新无标签 landing pad PLT：PLT 项使用 t2 代替 t3，PLT 头交换 t2/t3 且不再以 landing pad 开头，头大小与默认 PLT 头同为 32 字节；涉及 bfd/elfnn-riscv.c 和 ld 测试。
- 影响：该提交影响 RISC-V 链接器在 Zicfilp 下的 PLT 生成，与 psABI 对齐；作者称向后兼容，但元数据未提供上游测试执行结果，不能替代实际验证。
- 打包建议：该提交被判定为打包候选，建议人工确认目标 binutils 版本是否已合入，并检查 ld 测试 zicfilp-unlabeled-plt.d 及相关 psABI 变更是否被测试通过；在 RuyiSDK 中更新前需验证对既有 RISC-V 链接输出的影响。

### RISC-V: Fix the implied extensions of xsmtvdotii

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-08T07:24:34Z
- 作者：kito-cheng；SHA：cb663c0073900e7ed764459c1d659c1c85d9d155
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/cb663c0073900e7ed764459c1d659c1c85d9d155)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、keyword:compiler-option:-march、keyword:isa-extension:extension、keyword:isa-extension:zve32x、path:bfd/elfxx-riscv.c、path:gas/testsuite/gas/riscv/imply.d、path:gas/testsuite/gas/riscv/imply.s、token:risc-v、token:riscv、token:rv64
- 涉及文件：bfd/elfxx-riscv.c、gas/testsuite/gas/riscv/imply.d、gas/testsuite/gas/riscv/imply.s
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：修复 RISC-V 扩展隐含关系中的顺序错误：将 xsmtvdotii 排在 xsmtvdot 之前，以确保 -march=rv64i\_xsmtvdotii 能正确带入 xsmtvdot 隐含的 zve32x，并增加 imply 测试。
- 影响：此变更修复 RISC-V 汇编器或 BFD 对 ISA 扩展隐含关系的处理，涉及 -march 选项行为。已合入上游，但未经 RuyiSDK 构建或测试证实；对使用相关扩展选项的用户可能重要。
- 打包建议：规则判定为打包候选。建议人工确认该 bugfix 是否包含在所需 binutils 分支或版本中，运行 gas 的 imply 测试并核对 -march=rv64i\_xsmtvdotii 的实际扩展解析结果后再决定合入。


## 低优先级

### \[committed\]\[RISC-V\] Fix one more test fallout from AOP work on RISC-V

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-11T20:11:28Z
- 作者：Jeff Law；SHA：be2755d55421ace63363402901b4e0e2f07f798c
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/be2755d55421ace63363402901b4e0e2f07f798c)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、path:gcc/config/riscv/riscv.md、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/riscv.md
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 端口修复一个 AOP 相关测试失败：调整 \(x &lt;&lt; C1\) + C2 拆分器的条件，避免在启用 Zbkb 且移位量为半字长时错误触发。
- 影响：该提交修改 gcc/config/riscv/riscv.md，属于测试和代码生成的局部修正。状态为已合入上游提交；元数据称经过 bootstrap 和回归测试，但不能证明 RuyiSDK 已支持或已发布。
- 打包建议：规则未判定为打包候选。优先级较低，维护者可在常规上游同步时核对是否已包含；如无需特别处理 Zbkb 移位场景，可暂不单独跟踪。

### \[RISC-V\] Fix pack\* tests for RISC-V after any-or-plus changes

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-11T14:30:52Z
- 作者：Jeff Law；SHA：9d11ed33f54b395948521654218e2eb98c237b0e
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/9d11ed33f54b395948521654218e2eb98c237b0e)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:tests、path:gcc/config/riscv/crypto.md、path:gcc/config/riscv/iterators.md、path:gcc/config/riscv/riscv.cc、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/crypto.md、gcc/config/riscv/iterators.md、gcc/config/riscv/riscv.cc
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 端口修复 any-or-plus 补丁后的 pack\* 指令相关回归：引入 code iterator 以支持新增的 PLUS 形式，并同步调整 riscv\_rtx\_costs 中 pack 指令的代价计算。
- 影响：该提交修改 gcc/config/riscv/crypto.md、iterators.md 和 riscv.cc，主要解决 scan-asm 失败和代价模型问题。已合入上游；元数据提到 bootstrap 与回归测试，但来源状态仍为提交，不能视为正式发布或 RuyiSDK 已验证。
- 打包建议：规则未判定为打包候选。建议仅在同步 GCC RISC-V 后端时由维护者核对该提交是否随所需版本合入，并关注 pack 指令相关测试是否满足预期；不单独作为紧急打包项。
