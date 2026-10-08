# GNU RISC-V 上游更新报告

统计窗口（UTC）：2026-09-24T13:47:00Z 至 2026-10-08T06:51:00Z
生成时间（UTC）：2026-10-08T06:51:00Z

共 27 条相关更新：高 7、中 13、低 7。

优先级和打包候选由规则决定；LLM 辅助分析仅供参考，最终打包需人工评估和构建测试。
提交已合入不代表已经发布；关联 PR 的状态单独列出。

## 仓库采集状态

- RTEMS/sourceware-mirror-binutils-gdb：ok；分支 master
  采集窗口（UTC）：2026-09-24T13:47:00Z 至 2026-10-08T06:51:00Z
- gcc-mirror/gcc：ok；分支 master
  采集窗口（UTC）：2026-09-24T13:47:00Z 至 2026-10-08T06:51:00Z
- sailfishos-mirror/glibc：ok；分支 master
  采集窗口（UTC）：2026-09-24T13:47:00Z 至 2026-10-08T06:51:00Z

## 采集警告

- RTEMS/sourceware-mirror-binutils-gdb：轻量标签没有独立时间，只能用所指提交的时间代替。
- gcc-mirror/gcc：轻量标签没有独立时间，只能用所指提交的时间代替。
- 分页在第 1 页停止，元数据覆盖不完整。

## 高优先级

### RISC-V: Decode Zcmt JVT entries in objdump

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-01T09:35:04Z
- 作者：pz9115；SHA：7310b8560eae5292a1e2a5ff8c8b969506e1cece
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/7310b8560eae5292a1e2a5ff8c8b969506e1cece)
- 规则判断：high / isa-extension；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:isa-extension:zdinx、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt-base-rv32.d、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt-base-rv64.d、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt-rv32.d、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt-rv64.d、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt.ld、path:binutils/testsuite/binutils-all/riscv/zcmt-jvt.s、path:opcodes/riscv-dis.c、token:risc-v、token:riscv、token:rv32、token:rv64
- 涉及文件：binutils/testsuite/binutils-all/riscv/zcmt-jvt-base-rv32.d、binutils/testsuite/binutils-all/riscv/zcmt-jvt-base-rv64.d、binutils/testsuite/binutils-all/riscv/zcmt-jvt-rv32.d、binutils/testsuite/binutils-all/riscv/zcmt-jvt-rv64.d、binutils/testsuite/binutils-all/riscv/zcmt-jvt.ld、binutils/testsuite/binutils-all/riscv/zcmt-jvt.s、opcodes/riscv-dis.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / isa-extension（不改变规则判断）
- 中文摘要：该提交在 objdump 中解码 RISC-V Zcmt JVT 条目并注释 table-jump 目标，新增 RV32/RV64 且带/不带 base symbol 的手工测试表。
- 影响：增强对 Zcmt 跳转表反汇编的理解，涉及 opcodes/riscv-dis.c 和 binutils 测试；限于上游已合入提交，不代表已构建或测试通过，也未体现 RuyiSDK 是否启用。
- 打包建议：人工核对所用 binutils 版本是否包含该提交，按需合入并运行 binutils-all/riscv/zcmt-jvt 相关测试，确认 Zcmt 反汇编输出。

### RISC-V: Add supervisor architecture support

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-01T09:02:58Z
- 作者：jerryzj；SHA：6963071aac9ac1433ca3dc7558c300b9d43c1ef1
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/6963071aac9ac1433ca3dc7558c300b9d43c1ef1)
- 规则判断：high / profile-abi；打包候选：是，待人工评估
- 命中规则：functional:add、functional:support、keyword:profile-abi:profile、path:bfd/elfxx-riscv.c、path:gas/testsuite/gas/riscv/march-help.l、token:risc-v、token:riscv
- 涉及文件：bfd/elfxx-riscv.c、gas/testsuite/gas/riscv/march-help.l
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / profile-abi（不改变规则判断）
- 中文摘要：该提交为 RISC-V 增加 supervisor architecture v1.11/v1.12/v1.13（Ss1p11/Ss1p12/Ss1p13）支持。
- 影响：可能扩展 bfd/gas 对 RISC-V 扩展名和 profile 的识别能力，涉及 bfd/elfxx-riscv.c 和 gas 测试；上游已合入提交，需经版本核对和实际构建验证。
- 打包建议：核对 binutils 版本及合入状态，运行 gas/riscv march-help 测试，确认 Ss1p\* 扩展字符串解析和文档输出。

### RISC-V: Allow RVV register overlap for vfw{add,sub,mul}.vf

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-29T01:45:31Z
- 作者：Incarnation-p-lee；SHA：a3f5541bcf62d1142cea7f7f70afcabf888d947c
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/a3f5541bcf62d1142cea7f7f70afcabf888d947c)
- 规则判断：high / vector-crypto-hypervisor；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:vector-crypto-hypervisor:vector、path:gcc/config/riscv/vector.md、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/vector.md
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / vector-crypto-hypervisor（不改变规则判断）
- 中文摘要：该提交允许 vfwadd.vf、vfwsub.vf、vfwmul.vf 等 RVV 双倍宽浮点指令的寄存器重叠，利用 Wvr 约束。
- 影响：可能放宽寄存器分配限制，改善 RVV 浮点 widening 指令代码生成；仅上游已合入提交，实际效果需在目标 GCC 上测试。
- 打包建议：核对目标 GCC 版本包含该提交，运行 RISC-V RVV 向量测试，重点检查 vfw\*.vf 指令正确性和寄存器约束。

### RISC-V: Error out early for unsupported builtins. \[PR127553\]

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T18:55:41Z
- 作者：Robin Dapp；SHA：2b980c3e11a6b6ef0223d1668672bac877038185
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/2b980c3e11a6b6ef0223d1668672bac877038185)
- 规则判断：high / vector-crypto-hypervisor；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:vector-crypto-hypervisor:vector、path:gcc/config/riscv/riscv-vector-builtins.cc、path:gcc/testsuite/gcc.target/riscv/pr127553.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/bug-9.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-1.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-10.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-2.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-3.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-4.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-5.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-6.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-7.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-8.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-9.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr114988-1.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr114988-2.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr120436.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-17.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-18.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-19.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-20.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-21.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-22.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-23.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-24.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-25.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-26.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-27.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-28.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-29.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-3.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-7.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-8.c、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/riscv-vector-builtins.cc、gcc/testsuite/gcc.target/riscv/pr127553.c、gcc/testsuite/gcc.target/riscv/rvv/base/bug-9.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-1.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-10.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-2.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-3.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-4.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-5.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-6.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-7.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-8.c、gcc/testsuite/gcc.target/riscv/rvv/base/intrinsic\_required\_ext-9.c、gcc/testsuite/gcc.target/riscv/rvv/base/pr114988-1.c、gcc/testsuite/gcc.target/riscv/rvv/base/pr114988-2.c、gcc/testsuite/gcc.target/riscv/rvv/base/pr120436.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-17.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-18.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-19.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-20.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-21.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-22.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-23.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-24.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-25.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-26.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-27.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-28.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-29.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-3.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-7.c、gcc/testsuite/gcc.target/riscv/rvv/base/target\_attribute\_v\_with\_intrinsic-8.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / vector-crypto-hypervisor（不改变规则判断）
- 中文摘要：该提交在 check\_builtin\_call 阶段提前对不支持的 RISC-V RVV builtin 报错，避免调用被优化掉而缺少诊断，并调整相关测试预期。
- 影响：改变 RVV 内建函数的诊断时机和错误信息，可能影响依赖旧行为的编译检查；仅上游合入，需实际测试编译器兼容性。
- 打包建议：核对 GCC 版本，运行 pr127553 和 intrinsic\_required\_ext 系列测试，确认新增诊断位置及测试预期调整是否符合目标平台。

### RISC-V: Consider spills in conv-dynamic LMUL \[PR127075\].

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T18:55:41Z
- 作者：Robin Dapp；SHA：a924d879f01d00d6c29e870c51bebcbf5e5a96eb
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/a924d879f01d00d6c29e870c51bebcbf5e5a96eb)
- 规则判断：high / vector-crypto-hypervisor；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:vector-crypto-hypervisor:vector、path:gcc/config/riscv/riscv-vector-costs.cc、path:gcc/config/riscv/riscv-vector-costs.h、path:gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/pr127075.c、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/riscv-vector-costs.cc、gcc/config/riscv/riscv-vector-costs.h、gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/pr127075.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / vector-crypto-hypervisor（不改变规则判断）
- 中文摘要：该提交让 -mrvv-max-lmul=conv-dynamic 在 LMUL 决策中考虑 spill，合并 dynamic 的溢出估计并修正部分错误，同时重构相关代价函数并新增 PR127075 测试。
- 影响：可能改善 RVV 自动向量化在 conv-dynamic 模式下的寄存器溢出和代码生成质量，尤其影响 x264 等场景；上游已合入，需实际回归。
- 打包建议：核对目标 GCC 版本，运行 gcc.dg/vect/costmodel/riscv/rvv/pr127075.c 及相关 cost model 测试，评估 conv-dynamic 行为变化与性能。

### posix: Add POSIX posix\_spawn\_file\_actions\_add{,f}chdir

- 仓库：sailfishos-mirror/glibc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T15:57:36Z
- 作者：zatrazz；SHA：371d58d11bf7aacd4bf471bcb22bc7278330f349
- 来源：[原始记录](https://github.com/sailfishos-mirror/glibc/commit/371d58d11bf7aacd4bf471bcb22bc7278330f349)
- 规则判断：high / compiler-option；打包候选：是，待人工评估
- 命中规则：functional:add、keyword:compiler-option:option、path:sysdeps/unix/sysv/linux/riscv/rv32/libc.abilist、path:sysdeps/unix/sysv/linux/riscv/rv64/libc.abilist
- 涉及文件：NEWS、conform/data/spawn.h-data、posix/Makefile、posix/Versions、posix/spawn.h、posix/spawn\_faction\_addchdir.c、posix/spawn\_faction\_addfchdir.c、posix/tst-spawn-chdir-posix.c、posix/tst-spawn-chdir.c、sysdeps/mach/hurd/i386/libc.abilist、sysdeps/mach/hurd/x86\_64/libc.abilist、sysdeps/unix/sysv/linux/aarch64/libc.abilist、sysdeps/unix/sysv/linux/alpha/libc.abilist、sysdeps/unix/sysv/linux/arc/libc.abilist、sysdeps/unix/sysv/linux/arm/be/libc.abilist、sysdeps/unix/sysv/linux/arm/le/libc.abilist、sysdeps/unix/sysv/linux/csky/libc.abilist、sysdeps/unix/sysv/linux/hppa/libc.abilist、sysdeps/unix/sysv/linux/i386/libc.abilist、sysdeps/unix/sysv/linux/loongarch/ilp32/libc.abilist、sysdeps/unix/sysv/linux/loongarch/lp64/libc.abilist、sysdeps/unix/sysv/linux/m68k/coldfire/libc.abilist、sysdeps/unix/sysv/linux/m68k/m680x0/libc.abilist、sysdeps/unix/sysv/linux/microblaze/be/libc.abilist、sysdeps/unix/sysv/linux/microblaze/le/libc.abilist、sysdeps/unix/sysv/linux/mips/mips32/fpu/libc.abilist、sysdeps/unix/sysv/linux/mips/mips32/nofpu/libc.abilist、sysdeps/unix/sysv/linux/mips/mips64/n32/libc.abilist、sysdeps/unix/sysv/linux/mips/mips64/n64/libc.abilist、sysdeps/unix/sysv/linux/or1k/libc.abilist、sysdeps/unix/sysv/linux/powerpc/powerpc32/fpu/libc.abilist、sysdeps/unix/sysv/linux/powerpc/powerpc32/nofpu/libc.abilist、sysdeps/unix/sysv/linux/powerpc/powerpc64/be/libc.abilist、sysdeps/unix/sysv/linux/powerpc/powerpc64/le/libc.abilist、sysdeps/unix/sysv/linux/riscv/rv32/libc.abilist、sysdeps/unix/sysv/linux/riscv/rv64/libc.abilist、sysdeps/unix/sysv/linux/s390/libc.abilist、sysdeps/unix/sysv/linux/sh/be/libc.abilist、sysdeps/unix/sysv/linux/sh/le/libc.abilist、sysdeps/unix/sysv/linux/sparc/sparc32/libc.abilist、sysdeps/unix/sysv/linux/sparc/sparc64/libc.abilist、sysdeps/unix/sysv/linux/x86\_64/64/libc.abilist、sysdeps/unix/sysv/linux/x86\_64/x32/libc.abilist
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：glibc 为 POSIX.1-2024 添加 posix\_spawn\_file\_actions\_addchdir 和 fchdir 正式符号，替代原 \_np 别名，并调整声明可见性。
- 影响：影响 glibc 头文件和 ABI 符号导出，可能涉及 RISC-V abilist 更新；与 RISC-V ISA 无直接关系，上游已合入提交，不代表各发行版或 RuyiSDK 已同步。
- 打包建议：人工核对 glibc 版本及 RISC-V abilist 是否同步更新，运行 posix/tst-spawn-chdir\* 测试，确认符号声明和链接兼容。

### \[PATCH v2\] vect: Look through promotions for SAT\_TRUNC

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-27T17:34:07Z
- 作者：wangjue；SHA：19378ecd3851564bb168dd7779cb52c79193cb2d
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/19378ecd3851564bb168dd7779cb52c79193cb2d)
- 规则判断：high / vector-crypto-hypervisor；打包候选：是，待人工评估
- 命中规则：functional:add、functional:support、keyword:vector-crypto-hypervisor:vector、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/pr120378-3.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/pr120378-4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/sat-trunc-promote-1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/sat-trunc-promote-run-1.c、token:riscv、token:rv32、token:rv64
- 涉及文件：gcc/testsuite/gcc.target/riscv/rvv/autovec/pr120378-3.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/pr120378-4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/sat-trunc-promote-1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/sat-trunc-promote-run-1.c、gcc/tree-vect-patterns.cc
- 分析方式：LLM 辅助分析
- LLM 分类建议：high / vector-crypto-hypervisor（不改变规则判断）
- 中文摘要：该提交在向量化模式识别中为 SAT\_TRUNC 看穿类型提升，当较窄类型支持 MAX\_EXPR 和 SAT\_TRUNC 时使用单次非提升输入，避免冗余 widen-and-narrow，并新增 RISC-V RVV 测试。
- 影响：可能改善饱和截断自动向量化的代码生成，降低冗余扩展；上游已合入提交，需验证 RISC-V rv32/rv64 测试及性能。
- 打包建议：核对目标 GCC 版本，运行 gcc.target/riscv/rvv/autovec 下 sat-trunc-promote 相关测试，确认模式识别和生成序列符合预期。


## 中优先级

### OpenMP: Add the 'scaled' modifier to the 'simdlen' clause \[PR127723\]

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-07T04:37:19Z
- 作者：tob2；SHA：fbcafeec06a66175108be68c34aceafba7a453b9
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/fbcafeec06a66175108be68c34aceafba7a453b9)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、token:risc-v
- 涉及文件：gcc/attribs.cc、gcc/c/c-parser.cc、gcc/c/c-typeck.cc、gcc/cp/parser.cc、gcc/cp/pt.cc、gcc/cp/semantics.cc、gcc/gimplify.cc、gcc/omp-general.cc、gcc/omp-simd-clone.cc、gcc/testsuite/c-c++-common/gomp/simdlen-scaled-1.c、gcc/testsuite/c-c++-common/gomp/simdlen-scaled-2.c、gcc/testsuite/c-c++-common/gomp/simdlen-scaled-3.c、gcc/testsuite/c-c++-common/gomp/simdlen-scaled-4.c、gcc/testsuite/g++.dg/gomp/simdlen-scaled-1.C、gcc/testsuite/g++.dg/gomp/simdlen-scaled-2.C、gcc/tree-core.h、gcc/tree-pretty-print.cc、gcc/tree.cc、gcc/tree.h
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：该提交为 OpenMP 6.1 simdlen 子句添加 scaled 修饰符，支持 C/C++ 解析和 declare variant 上下文选择，但在 gimplify 与 simd clone 阶段暂时报 sorry。
- 影响：增加 OpenMP 前端语法支持，与 RISC-V/AArch64 的 simdlen 变体相关，但当前功能未完全实现；上游已合入提交，不应视为可直接使用。
- 打包建议：核对 GCC 版本，测试 OpenMP scaled simdlen 的解析和 sorry 路径，等待后续 gimplify/simd-clone 实现补丁后再评估完整支持。

### vect: Fix scalar iteration bounds when doing alignment peeling with partial vectors \[PR127677\]

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-02T12:20:24Z
- 作者：TamarChristinaArm；SHA：d7bd302654fab2ddd8d7e8539f163db63a2f07e5
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/d7bd302654fab2ddd8d7e8539f163db63a2f07e5)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、keyword:compiler-option:-mabi、keyword:compiler-option:-march、keyword:isa-extension:zvl、keyword:vector-crypto-hypervisor:vector、keyword:vector-crypto-hypervisor:vectorization、token:risc-v、token:rv64
- 涉及文件：gcc/testsuite/gcc.dg/vect/vect-early-break\_146-pr127677.c、gcc/tree-vect-loop-manip.cc
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：修复 GCC 向量化在启用部分向量和对齐剥离时，标量迭代边界可能下溢的问题（PR127677）。示例中 RISC-V rv64gcv\_zvl256b 下，当 niters 小于 prolog\_niters 时，remainder 计算出现无符号下溢，导致错误边界。
- 影响：该问题可能影响 RISC-V RVV 向量化循环的正确性，尤其在使用 -mrvv-vector-bits=zvl、显式 LMUL 时。当前信息仅表明上游提交已合入，未确认是否已构建、测试或随 RuyiSDK 工具链发布，需人工核对具体版本合入情况。
- 打包建议：建议确认该提交是否已包含在目标 GCC/RuyiSDK 工具链版本中；若启用 RVV 对齐剥离场景，可运行新增测试 gcc.dg/vect/vect-early-break\_146-pr127677.c 并核对 tree-vect-loop-manip.cc 变更，评估对 -march=rv64gcv\_zvl256b 等选项的影响。

### RISC-V: Fix h-&gt;got union phase confusion for DT\_RELR

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-02T09:49:33Z
- 作者：Jens Remus；SHA：e522ebecf7381e1e03548a7d0816b8ce3c038984
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/e522ebecf7381e1e03548a7d0816b8ce3c038984)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：修复 RISC-V 链接器中 DT\_RELR 处理时 h-&gt;got 联合体阶段混淆的问题：allocate\_dynrelocs 已将 refcount 语义改为 offset 语义后，record\_relr\_dyn\_got\_relocs 仍按旧语义判断，导致 GOT 条目状态误判。
- 影响：该修复影响 RISC-V 链接器生成 DT\_RELR 相对重定位时的正确性，可能避免错误判断未分配 GOT 条目。当前仅见上游合并提交，构建、测试及在 RuyiSDK/binutils 中的实际可用性需人工确认。
- 打包建议：建议核对目标 binutils 版本是否包含该提交；如启用 DT\_RELR/相对重定位打包，需结合新增的 RISC-V DT\_RELR 测试和实际链接用例验证 GOT 与相对重定位生成结果。

### RISC-V: Add Zcmt table-jump relocation definitions

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-01T09:35:04Z
- 作者：pz9115；SHA：4b013df1822f977e2d9ceeeabc0eb2f827f66c03
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/4b013df1822f977e2d9ceeeabc0eb2f827f66c03)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:include/elf/riscv.h、path:include/opcode/riscv.h、token:risc-v、token:riscv
- 涉及文件：include/elf/riscv.h、include/opcode/riscv.h
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / isa-extension（不改变规则判断）
- 中文摘要：在 binutils 中为 RISC-V 添加 Zcmt 表跳转（table-jump）的链接器内部标记和指令编码定义，包括 R\_RISCV\_TABLE\_JUMP 重定位号、相关符号名、段名及 Zcmt 常量。
- 影响：该提交为 Zcmt 后续放松/链接支持提供基础定义，但目前仅为内部标记，尚无公开 ELF 重定位或 howto 条目，功能可能不完整。上游已合入提交，无法证明已启用或通过完整测试，RuyiSDK 支持状态待确认。
- 打包建议：建议仅将该提交作为 Zcmt 支持的基础定义纳入评估，确认目标 binutils 版本合入情况；若产品需要完整 Zcmt 表跳转支持，还需检查后续实现和测试，不宜仅凭此提交判断功能可用。

### RISC-V: PR30237, don't add PT\_RISCV\_ATTRIBUTES in objcopy/strip

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-01T08:49:22Z
- 作者：OctopusET；SHA：97e4144904779d0c986670ed977d7c3fa61806b2
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/97e4144904779d0c986670ed977d7c3fa61806b2)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:bfd/elfnn-riscv.c、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：修复 objcopy/strip 处理 RISC-V 二进制时可能添加 PT\_RISCV\_ATTRIBUTES 程序头导致布局失败的问题（PR30237）。当 info 为 NULL 时跳过添加，类似 SPU/S390/HPPA 的处理。
- 影响：该问题会导致对 LLD 早期版本生成的无 PT\_RISCV\_ATTRIBUTES 二进制执行 objcopy/strip 时出现 not enough room for program headers 错误。当前仅为上游合并提交，实际 binutils 构建和测试状态需人工确认。
- 打包建议：建议核对目标 binutils 版本是否已合入该修复，并对无 PT\_RISCV\_ATTRIBUTES 的 RISC-V 二进制执行 objcopy/strip 做回归测试，确认不再破坏程序头布局。

### RISC-V: Added DT\_RELR support

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-10-01T08:23:17Z
- 作者：Nelson Chu；SHA：b0c84e4cd5dae13d186b6099c080137d250a986a
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/b0c84e4cd5dae13d186b6099c080137d250a986a)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、path:bfd/elfnn-riscv.c、path:ld/emulparams/elf32lriscv-defs.sh、path:ld/testsuite/ld-riscv-elf/discard-pic.d、path:ld/testsuite/ld-riscv-elf/discard.ld、path:ld/testsuite/ld-riscv-elf/discard.s、path:ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、path:ld/testsuite/ld-riscv-elf/relr-addend.d、path:ld/testsuite/ld-riscv-elf/relr-addend.s、path:ld/testsuite/ld-riscv-elf/relr-align-rv32-pic.d、path:ld/testsuite/ld-riscv-elf/relr-align-rv32-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-align-rv64-pic.d、path:ld/testsuite/ld-riscv-elf/relr-align-rv64-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-align.s、path:ld/testsuite/ld-riscv-elf/relr-data-rv32-pic.d、path:ld/testsuite/ld-riscv-elf/relr-data-rv32-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-data-rv32-pie.d、path:ld/testsuite/ld-riscv-elf/relr-data-rv32-pie.rd、path:ld/testsuite/ld-riscv-elf/relr-data-rv64-pic.d、path:ld/testsuite/ld-riscv-elf/relr-data-rv64-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-data-rv64-pie.d、path:ld/testsuite/ld-riscv-elf/relr-data-rv64-pie.rd、path:ld/testsuite/ld-riscv-elf/relr-data.s、path:ld/testsuite/ld-riscv-elf/relr-discard-pic.d、path:ld/testsuite/ld-riscv-elf/relr-discard-pie.d、path:ld/testsuite/ld-riscv-elf/relr-got-rv32-pic.d、path:ld/testsuite/ld-riscv-elf/relr-got-rv32-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-got-rv32-pie.d、path:ld/testsuite/ld-riscv-elf/relr-got-rv32-pie.rd、path:ld/testsuite/ld-riscv-elf/relr-got-rv64-pic.d、path:ld/testsuite/ld-riscv-elf/relr-got-rv64-pic.rd、path:ld/testsuite/ld-riscv-elf/relr-got-rv64-pie.d、path:ld/testsuite/ld-riscv-elf/relr-got-rv64-pie.rd、path:ld/testsuite/ld-riscv-elf/relr-got-start.d、path:ld/testsuite/ld-riscv-elf/relr-got-start.s、path:ld/testsuite/ld-riscv-elf/relr-got.s、path:ld/testsuite/ld-riscv-elf/relr-relax.d、path:ld/testsuite/ld-riscv-elf/relr-relax.s、path:ld/testsuite/ld-riscv-elf/relr-relocs.ld、path:ld/testsuite/ld-riscv-elf/relr-textrel-pic.d、path:ld/testsuite/ld-riscv-elf/relr-textrel-pie.d、path:ld/testsuite/ld-riscv-elf/relr-textrel.s、token:risc-v、token:riscv
- 涉及文件：bfd/elfnn-riscv.c、binutils/readelf.c、binutils/testsuite/lib/binutils-common.exp、ld/NEWS、ld/emulparams/elf32lriscv-defs.sh、ld/ld.texi、ld/testsuite/ld-riscv-elf/discard-pic.d、ld/testsuite/ld-riscv-elf/discard.ld、ld/testsuite/ld-riscv-elf/discard.s、ld/testsuite/ld-riscv-elf/ld-riscv-elf.exp、ld/testsuite/ld-riscv-elf/relr-addend.d、ld/testsuite/ld-riscv-elf/relr-addend.s、ld/testsuite/ld-riscv-elf/relr-align-rv32-pic.d、ld/testsuite/ld-riscv-elf/relr-align-rv32-pic.rd、ld/testsuite/ld-riscv-elf/relr-align-rv64-pic.d、ld/testsuite/ld-riscv-elf/relr-align-rv64-pic.rd、ld/testsuite/ld-riscv-elf/relr-align.s、ld/testsuite/ld-riscv-elf/relr-data-rv32-pic.d、ld/testsuite/ld-riscv-elf/relr-data-rv32-pic.rd、ld/testsuite/ld-riscv-elf/relr-data-rv32-pie.d、ld/testsuite/ld-riscv-elf/relr-data-rv32-pie.rd、ld/testsuite/ld-riscv-elf/relr-data-rv64-pic.d、ld/testsuite/ld-riscv-elf/relr-data-rv64-pic.rd、ld/testsuite/ld-riscv-elf/relr-data-rv64-pie.d、ld/testsuite/ld-riscv-elf/relr-data-rv64-pie.rd、ld/testsuite/ld-riscv-elf/relr-data.s、ld/testsuite/ld-riscv-elf/relr-discard-pic.d、ld/testsuite/ld-riscv-elf/relr-discard-pie.d、ld/testsuite/ld-riscv-elf/relr-got-rv32-pic.d、ld/testsuite/ld-riscv-elf/relr-got-rv32-pic.rd、ld/testsuite/ld-riscv-elf/relr-got-rv32-pie.d、ld/testsuite/ld-riscv-elf/relr-got-rv32-pie.rd、ld/testsuite/ld-riscv-elf/relr-got-rv64-pic.d、ld/testsuite/ld-riscv-elf/relr-got-rv64-pic.rd、ld/testsuite/ld-riscv-elf/relr-got-rv64-pie.d、ld/testsuite/ld-riscv-elf/relr-got-rv64-pie.rd、ld/testsuite/ld-riscv-elf/relr-got-start.d、ld/testsuite/ld-riscv-elf/relr-got-start.s、ld/testsuite/ld-riscv-elf/relr-got.s、ld/testsuite/ld-riscv-elf/relr-relax.d、ld/testsuite/ld-riscv-elf/relr-relax.s、ld/testsuite/ld-riscv-elf/relr-relocs.ld、ld/testsuite/ld-riscv-elf/relr-textrel-pic.d、ld/testsuite/ld-riscv-elf/relr-textrel-pie.d、ld/testsuite/ld-riscv-elf/relr-textrel.s
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：为 RISC-V 添加 DT\_RELR 相对重定位支持，参考 AArch64 和 LoongArch 实现；涵盖链接器生成 .relr.dyn、readelf 过滤 RISC-V 特殊符号、RISC-V 下的松弛安全性处理及相关测试和文档。
- 影响：这是一项新功能，可让 RISC-V 使用 DT\_RELR 压缩相对重定位；但与松弛存在交互，需确保更新节布局时不做不安全松弛。当前信息仅表示上游提交已合入，未确认是否通过测试或在 RuyiSDK/binutils 中默认启用。
- 打包建议：建议人工核对 binutils 版本是否包含完整 DT\_RELR 支持，并结合 ld-riscv-elf 新增 relr 测试、-z pack-relative-relocs 选项及实际链接场景验证；注意确认该项新功能是否经过目标工具链测试和发布流程。

### RISC-V: Spill more unsplittable moves \[PR127484\].

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T18:55:40Z
- 作者：Robin Dapp；SHA：3d79c978b53474d2b613fe3e28037393c8d037b0
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/3d79c978b53474d2b613fe3e28037393c8d037b0)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:gcc/config/riscv/riscv.cc、path:gcc/config/riscv/riscv.md、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/pr127484.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/pr127547.c、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/riscv.cc、gcc/config/riscv/riscv.md、gcc/testsuite/gcc.target/riscv/rvv/autovec/pr127484.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/pr127547.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：修复 RISC-V 在 32 位目标上某些不可拆分 quadword move（如 TFmode 及复杂 int128）的溢出处理，扩展 riscv\_subpart 以处理任意模式子部分，并按字大小分块移动溢出的 TFmode 值（PR127484、PR127547）。
- 影响：该修复影响 RISC-V 后端在 32 位目标上处理 TFmode/int128 类宽值移动的正确性，尤其涉及 subreg 和溢出代码。当前仅见上游合并提交，未确认已构建、测试或随 RuyiSDK 发布。
- 打包建议：建议确认目标 GCC 版本是否包含该提交，并在 rv32 目标上运行新增测试 gcc.target/riscv/rvv/autovec/pr127484.c 与 pr127547.c，验证宽类型移动和溢出路径是否修复。

### RISC-V: Compute live ranges for pattern results

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T15:19:37Z
- 作者：garthlei；SHA：b0434879418053061782e825ea0bf2eadb654b2b
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/b0434879418053061782e825ea0bf2eadb654b2b)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:regression、keyword:vector-crypto-hypervisor:vector、keyword:vector-crypto-hypervisor:vectorization、path:gcc/config/riscv/riscv-vector-costs.cc、path:gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul4-5.c、path:gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul4-7.c、path:gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul8-16.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/pr121910.c、token:risc-v、token:riscv、token:rv32、token:rv64
- 涉及文件：gcc/config/riscv/riscv-vector-costs.cc、gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul4-5.c、gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul4-7.c、gcc/testsuite/gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul8-16.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/pr121910.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：改进 RISC-V 向量化成本模型：当语句被模式语句替换时，改为计算模式结果的活跃范围，而非原始变量的活跃范围，以提高寄存器压力估算精度。
- 影响：该变更可能改善 RVV 动态 LMUL 选择和寄存器压力估算，但属于启发式优化，可能带来代码生成差异。上游提交称已对 rv64gcv/rv32gcv 回归测试无回归，但元数据未提供完整测试结果，RuyiSDK 实际影响需核对。
- 打包建议：建议在包含 RVV 成本模型优化的工具链中核对该提交；重点运行 gcc.dg/vect/costmodel/riscv/rvv/dynamic-lmul4-5.c、dynamic-lmul4-7.c、dynamic-lmul8-16.c 及 pr121910.c，并评估对动态 LMUL 决策的影响。

### RISC-V: Add conditional negate expansion \[PR126245\]

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T04:29:20Z
- 作者：naveengowda-gcc；SHA：ec09d7005033eb1f28304af80d888b81bb3063c7
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/ec09d7005033eb1f28304af80d888b81bb3063c7)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:gcc/config/riscv/riscv.md、path:gcc/testsuite/gcc.target/riscv/pr126245-negcc.c、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/riscv.md、gcc/testsuite/gcc.target/riscv/pr126245-negcc.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：为 RISC-V 添加条件取负展开：对整数比较结果将 X ? -X : X 展开为比较掩码、XOR 和加法序列，供现有 if-conversion 路径使用（PR126245）。
- 影响：该变更为整数条件取负操作提供新的展开方式，可能改善某些 if-conversion 场景下的代码生成，但不改变架构支持。当前仅见上游提交已合入，未确认在目标工具链中的测试和发布状态。
- 打包建议：建议人工核对目标 GCC 版本是否包含该提交，并运行新增测试 gcc.target/riscv/pr126245-negcc.c；如有依赖条件取负优化的场景，需评估该展开对代码大小和性能的影响。

### \[PATCH\]\[PR tree-optimization/126462\] Fix reassociation exposing rotate+xor to work correctly for int128 and BitInt

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-27T14:54:33Z
- 作者：JeffreyALaw；SHA：55867c37ec0dd0c4f1872183a6e43ea7dc16d479
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/55867c37ec0dd0c4f1872183a6e43ea7dc16d479)
- 规则判断：medium / bugfix；打包候选：是，待人工评估
- 命中规则：keyword:bugfix:fix、token:riscv
- 涉及文件：gcc/match.pd、gcc/testsuite/gcc.dg/torture/pr126462.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：GCC 树优化修复：重写 match.pd 中用于暴露 rotate+xor 模式的 xor 常量处理，从 HOST\_WIDE\_INT 接口改为 wi:: 接口，使 int128 和 \_BitInt 场景也能正确参与重关联，并新增 torture 测试 pr126462.c。提交说明提到已在 x86、aarch64、RISC-V 上引导并回归测试。
- 影响：这是通用中间端缺陷修复，RISC-V 是验证平台之一；可能避免 int128/\_BitInt 相关优化阶段产生错误代码或错过 rotate+xor 识别。但元数据仅代表上游已合入，不能证明 RuyiSDK 所用 GCC 版本已包含该提交，也不能证明对应构建/测试通过。实际影响需结合目标 GCC 分支和 RISC-V 后端回归结果确认。
- 打包建议：若打包 RISC-V GCC，需人工核对提交是否已进入目标版本分支或需要回合；评估 match.pd 改动对向量/标量优化的回归风险，并至少在 RISC-V 上运行相关 torture 用例。上游声称已测试，但仍需本地构建和回归验证后再决定合入发布包。

### LoongArch: Enable shared library and PIE support for loongarch\*-elf

- 仓库：RTEMS/sourceware-mirror-binutils-gdb；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-27T01:45:26Z
- 作者：Mintsuki；SHA：196286d25ccc652dc086ae173d1cfa836bed0618
- 来源：[原始记录](https://github.com/RTEMS/sourceware-mirror-binutils-gdb/commit/196286d25ccc652dc086ae173d1cfa836bed0618)
- 规则判断：medium / other；打包候选：否
- 命中规则：token:risc-v
- 涉及文件：ld/emulparams/elf32loongarch-defs.sh、ld/emulparams/elf64loongarch-defs.sh
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：Binutils/GDB 的 LoongArch ELF 目标启用共享库和 PIE 脚本支持：将 elf32loongarch-defs.sh 与 elf64loongarch-defs.sh 中的 GENERATE\_SHLIB\_SCRIPT、GENERATE\_PIE\_SCRIPT 设为无条件启用。提交说明称理由与同一系列中的 RISC-V 补丁相同，并记录由 Claude 辅助、Mintsuki 签署。
- 影响：该提交针对 loongarch\*-elf，不直接修改 RISC-V 代码路径；仅在提交说明中引用 RISC-V 补丁作为理由。对 RISC-V 工具链本身预期无直接影响，除非 RuyiSDK 同时打包多架构 binutils 并关注 LoongArch ELF 行为。元数据只代表上游已合入，不代表 RuyiSDK 已构建或支持相关目标。
- 打包建议：如仅维护 RISC-V 工具链，可将其视为非关键变更观察；若打包包含 LoongArch 的 binutils，需人工确认该提交已合入目标分支，并评估 ELF 目标启用 -shared/-pie 后对链接行为及测试套件的影响。上游未给出 RISC-V 验证结论。

### RISC-V: Update ARC-V RMX-100 load latency

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-25T21:08:37Z
- 作者：MichielDerhaeg；SHA：0de4790181fcf74665c3c27e901559a16d3e4991
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/0de4790181fcf74665c3c27e901559a16d3e4991)
- 规则判断：medium / other；打包候选：否
- 命中规则：path:gcc/config/riscv/arcv-rmx100.md、token:risc-v、token:riscv
- 涉及文件：gcc/config/riscv/arcv-rmx100.md
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / other（不改变规则判断）
- 中文摘要：GCC RISC-V 后端更新 ARC-V RMX-100 调度模型：将 load 指令延迟从更保守的最坏情况调整为更可能出现的典型值，并合并浮点 load 指令定义；同时提到 ARC 品牌/IP 已被 MIPS 收购，更新相关品牌表述。文件为 gcc/config/riscv/arcv-rmx100.md。
- 影响：仅影响 RISC-V 下针对 ARC-V RMX-100 的指令调度延迟，不改变功能语义；可能改变相关核的指令调度和性能。元数据仅说明上游已合入，未提供 RISC-V 构建或性能测试结果；需人工确认该调度模型是否被 RuyiSDK 目标启用。
- 打包建议：若 RuyiSDK 的 RISC-V GCC 启用了 ARC-V RMX-100 pipeline 描述或面向相关芯片优化，需人工核对此提交所在分支和版本，并评估调度变化对性能/代码尺寸的影响；若未启用该特定核模型，可作为低优先级上游变化观察。

### string: Drop always\_inline from tst-xbzero-opt \[BZ \#23130\]

- 仓库：sailfishos-mirror/glibc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-25T11:13:56Z
- 作者：shalseth；SHA：e066af409a8de7c6ceea099a4ff6810c021f341f
- 来源：[原始记录](https://github.com/sailfishos-mirror/glibc/commit/e066af409a8de7c6ceea099a4ff6810c021f341f)
- 规则判断：medium / other；打包候选：否
- 命中规则：token:risc-v
- 涉及文件：string/tst-xbzero-opt.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：medium / bugfix（不改变规则判断）
- 中文摘要：glibc 测试用例修复：从 string/tst-xbzero-opt.c 的 prepare\_test\_buffer 上去掉 always\_inline 属性及相关条件。提交说明指出 RISC-V GCC 具有 indirect\_return，使用 generic bits/indirect-return.h，导致测试请求内联调用 returns\_twice 的函数而构建失败；该修补已在 x86\_64 和 sparc64 上测试。
- 影响：修复 RISC-V 上 glibc 测试构建失败问题，不改变 glibc 运行库功能代码。元数据仅代表上游已合入，测试中未提及 RISC-V 平台验证；需确认该测试调整能否在目标 RISC-V 工具链和 glibc 版本上通过。
- 打包建议：如果 RuyiSDK 维护 glibc 包并运行其测试套件，需人工确认该提交已进入目标 glibc 版本/分支；建议在 RISC-V 上执行 string/tst-xbzero-opt 构建和测试，验证不再出现 setjmp 内联错误。此改动仅影响测试，不涉及运行库功能代码。


## 低优先级

### RISC-V: Add test cases for vfwadd.vf reg overlap

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-29T01:45:31Z
- 作者：Incarnation-p-lee；SHA：3d5f011ffec35d928577f5cfd24c101c5950ae93
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/3d5f011ffec35d928577f5cfd24c101c5950ae93)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-mf2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-mf4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-mf2.c、test-only、token:risc-v、token:riscv
- 涉及文件：gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-mf2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f16-mf4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwadd\_vf-f32-mf2.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 测试用例新增：为 RVV 自动向量化下的 vfwadd.vf 寄存器组重叠场景添加 f16/f32、m1/m2/m4/mf2/mf4 等 9 个新测试文件。提交说明强调并非尽可能多地制造重叠。
- 影响：纯测试新增，不改变编译器功能代码；影响仅是增强对 vfwadd.vf 寄存器重叠行为的上游测试覆盖。元数据只表明测试已合入上游，不能证明这些用例在当前 RuyiSDK RISC-V GCC 上已构建或通过。
- 打包建议：属于测试资产，通常无需单独打包；若 RuyiSDK 维护 GCC 测试套件或回归看板，可关注这些用例是否合入目标 GCC 分支，并仅在需要完整测试覆盖时合入包内测试源码。无需作为功能修复发布。

### RISC-V: Remove xfail of the vfwadd.vf reg overlap test case

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-29T01:45:31Z
- 作者：Incarnation-p-lee；SHA：5454af039f44aecefbd30fca712e2c5ca0714c5b
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/5454af039f44aecefbd30fca712e2c5ca0714c5b)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-25.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-26.c、path:gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-27.c、test-only、token:risc-v、token:riscv
- 涉及文件：gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-25.c、gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-26.c、gcc/testsuite/gcc.target/riscv/rvv/base/pr112431-27.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 测试调整：移除 pr112431-25.c、pr112431-26.c、pr112431-27.c 中对 csrr 检查的 xfail，因为 vfwadd.vf 的 RVV 寄存器组重叠现已被允许。
- 影响：纯测试预期调整，不改变编译器实现；反映上游对 vfwadd.vf 重叠合法性的判断变化，使相关测试从期望失败转为期望通过。元数据仅说明上游合入，不代表目标 GCC 分支已有相应功能或测试结果。
- 打包建议：无需作为独立功能打包；若维护 GCC 测试套件，应确认对应的 vfwadd.vf 寄存器组重叠支持已合入相同分支，否则移除 xfail 可能导致测试误通过或失败。人工核对目标版本后决定是否同步。

### RISC-V: Add test cases for vfwsub.vf reg overlap

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-29T01:45:31Z
- 作者：Incarnation-p-lee；SHA：5d2597a0b61da3c48c2f9dd3768c9806c980bbf8
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/5d2597a0b61da3c48c2f9dd3768c9806c980bbf8)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-mf2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-mf4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-mf2.c、test-only、token:risc-v、token:riscv
- 涉及文件：gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-mf2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f16-mf4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwsub\_vf-f32-mf2.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 测试用例新增：为 RVV 自动向量化下的 vfwsub.vf 寄存器组重叠场景添加 f16/f32、m1/m2/m4/mf2/mf4 等 9 个新测试文件。
- 影响：纯测试新增，不改变编译器功能；仅增加 vfwsub.vf 寄存器组重叠的上游覆盖。元数据不能证明这些测试已在 RuyiSDK 所用 GCC 版本上构建或通过。
- 打包建议：测试源码变更，通常无需单独打包；如需维护完整测试套件，可关注是否合入目标分支并执行相关 RVV 自动向量化用例。人工确认无功能代码变更，不作为缺陷修复或特性发布。

### RISC-V: Add test cases for vfwmul.vf reg overlap

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-29T01:45:31Z
- 作者：Incarnation-p-lee；SHA：ba20ee9a2cd5791cf571c873dbf331cdfbe6181d
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/ba20ee9a2cd5791cf571c873dbf331cdfbe6181d)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-mf2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-mf4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m1.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m2.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m4.c、path:gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-mf2.c、test-only、token:risc-v、token:riscv
- 涉及文件：gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-mf2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f16-mf4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m1.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m2.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-m4.c、gcc/testsuite/gcc.target/riscv/rvv/autovec/group\_overlap/vfwmul\_vf-f32-mf2.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC RISC-V 测试用例新增：为 RVV 自动向量化下的 vfwmul.vf 寄存器组重叠场景添加 f16/f32、m1/m2/m4/mf2/mf4 等 9 个新测试文件。
- 影响：纯测试新增，不改变编译器实现；仅增强 vfwmul.vf 寄存器组重叠测试覆盖。元数据只代表上游已合入，不等同于 RuyiSDK 已构建或测试通过。
- 打包建议：测试资产，通常无需单独打包；若维护 GCC 测试套件，应人工核对这些用例是否随目标版本合入，并在所需 RISC-V 目标上运行，确保测试本身有效。无需作为功能修复发布。

### elf: Only build THP tests for ABIs that define THP-PAGE-SIZE

- 仓库：sailfishos-mirror/glibc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-28T15:57:39Z
- 作者：zatrazz；SHA：60b925c18fe6436e0885b2be9fde5d8db3688cbb
- 来源：[原始记录](https://github.com/sailfishos-mirror/glibc/commit/60b925c18fe6436e0885b2be9fde5d8db3688cbb)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:tests、token:riscv
- 涉及文件：sysdeps/unix/sysv/linux/Makefile、sysdeps/unix/sysv/linux/aarch64/Makefile、sysdeps/unix/sysv/linux/alpha/Makefile、sysdeps/unix/sysv/linux/arc/Makefile、sysdeps/unix/sysv/linux/csky/Makefile、sysdeps/unix/sysv/linux/hppa/Makefile、sysdeps/unix/sysv/linux/i386/Makefile、sysdeps/unix/sysv/linux/loongarch/Makefile、sysdeps/unix/sysv/linux/m68k/Makefile、sysdeps/unix/sysv/linux/microblaze/Makefile、sysdeps/unix/sysv/linux/mips/Makefile、sysdeps/unix/sysv/linux/or1k/Makefile、sysdeps/unix/sysv/linux/powerpc/Makefile、sysdeps/unix/sysv/linux/s390/Makefile、sysdeps/unix/sysv/linux/sh/Makefile
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：glibc 上游合入一项提交，调整 THP 测试的构建条件：仅对定义了 THP-PAGE-SIZE 的 ABI 构建相关测试，并为各架构设置合适值，其中 RISC-V 64 位设置为 2MB。
- 影响：该改动主要涉及 glibc 测试体系中的 THP 相关用例，属于测试条件与架构参数调整，不直接改变运行时功能代码。元数据仅显示提交已合入，无法确认对应版本是否已构建、测试通过或已被 RuyiSDK 支持，需人工核对具体 glibc 版本与测试状态。
- 打包建议：规则判定不涉及打包候选。若维护 glibc 包或测试套件，可关注该提交是否进入目标版本，并人工核对 riscv64 上 THP 测试是否按预期启用或跳过；普通工具链或运行时打包通常无需单独处理此测试改动。

### \[RISC-V\] Fix typo and minor bugs in recently added bclr test

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-27T17:35:55Z
- 作者：JeffreyALaw；SHA：56805976a1cb252253118e8da40873857d6b0c9f
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/56805976a1cb252253118e8da40873857d6b0c9f)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、low-value:typo、path:gcc/testsuite/gcc.target/riscv/bclr-lowest-set-bit-2.c、test-only、token:risc-v、token:riscv、token:rv32、token:rv64
- 涉及文件：gcc/testsuite/gcc.target/riscv/bclr-lowest-set-bit-2.c
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC 上游合入一项测试用例修复，修正最近添加的 bclr 测试中的笔误，并强制使用 c99 模式，提交说明提到已在 riscv32-elf 和 riscv64-elf 上测试。
- 影响：该提交仅修改 gcc.target/riscv 下的测试文件，属于测试用例本身修正，不涉及编译器功能代码或代码生成逻辑。元数据只能说明上游已合入该提交，不能证明目标 GCC 版本已包含或已通过发布测试，需人工核对具体版本合入情况。
- 打包建议：规则判定不涉及打包候选。建议在打包 GCC 时将其视为常规测试用例更新，无需单独处理；若关注 RISC-V 测试套件稳定性，可确认对应分支是否已包含该修复，并人工运行相关 bclr 测试验证。

### middle-end: fix self-test fails \[PR127618\]

- 仓库：gcc-mirror/gcc；类型：commit；状态：已合入
- 提交时间（committer date）（UTC）：2026-09-26T16:18:43Z
- 作者：TamarChristinaArm；SHA：090ff9c73c79ab83eea66a010887a0ca8002ec6e
- 来源：[原始记录](https://github.com/gcc-mirror/gcc/commit/090ff9c73c79ab83eea66a010887a0ca8002ec6e)
- 规则判断：low / other；打包候选：否
- 命中规则：low-value:test、token:rv64
- 涉及文件：gcc/fold-const.cc
- 分析方式：LLM 辅助分析
- LLM 分类建议：low / other（不改变规则判断）
- 中文摘要：GCC 上游合入一项 middle-end 自测修复，解决 PR127618 自测失败问题：将相关测试中的 in\_nelts.coeffs\[0\] 改为 min\_out\_nelts，以避免 VLA 使用错误编码。提交说明提到在 aarch64 及多个 rv64 配置上检查过。
- 影响：该改动位于 GCC fold-const.cc 自测代码，主要影响构建期间自测稳定性，并非 RISC-V 专有功能改动，但提交说明中包含 rv64gc、rv64gcv 等 RISC-V 配置检查。元数据仅显示提交已合入，无法确认对应发布版本已包含或已通过完整测试，需人工核对目标 GCC 版本与自测结果。
- 打包建议：规则判定不涉及打包候选。建议在打包 GCC 时关注该提交是否进入所需分支，并人工核对 RISC-V 配置下的自测是否通过；通常无需单独出包，但可将其作为上游自测修复纳入常规版本跟进。
