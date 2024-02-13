<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><h1 tabindex="-1" dir="auto"><a id="user-content-picorv32---a-size-optimized-risc-v-cpu" class="anchor" aria-hidden="true" tabindex="-1" href="#picorv32---a-size-optimized-risc-v-cpu"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 - 尺寸优化的 RISC-V CPU</font></font></h1>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32是一个实现</font></font><a href="http://riscv.org/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">RISC-V RV32IMC指令集的</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CPU内核。它可配置为 RV32E、RV32I、RV32IC、RV32IM 或 RV32IMC 内核，并可选择包含内置中断控制器。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">工具（gcc、binutils 等）可以通过</font></font><a href="https://riscv.org/software-status/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">RISC-V 网站</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获取。与 PicoRV32 捆绑在一起的示例期望各种 RV32 工具链安装在</font></font><code>/opt/riscv32i[m][c]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.有关详细信息，</font><font style="vertical-align: inherit;">请参阅</font></font><a href="#building-a-pure-rv32i-toolchain"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">下面的构建说明</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。现在许多 Linux 发行版都包含 RISC-V 工具（例如 Ubuntu 20.04 就有</font></font><code>gcc-riscv64-unknown-elf</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）。使用相应设置进行编译
</font></font><code>TOOLCHAIN_PREFIX</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（例如</font></font><code>make TOOLCHAIN_PREFIX=riscv64-unknown-elf-</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="http://en.wikipedia.org/wiki/ISC_license" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 是根据ISC 许可证</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
（与 MIT 许可证或 2 条款 BSD 许可证类似的许&ZeroWidthSpace;&ZeroWidthSpace;可证）</font><font style="vertical-align: inherit;">授权的免费开放硬件。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-table-of-contents" class="anchor" aria-hidden="true" tabindex="-1" href="#table-of-contents"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">目录</font></font></h4>
<ul dir="auto">
<li><a href="#features-and-typical-applications"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">特点和典型应用</font></font></a></li>
<li><a href="#files-in-this-repository"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此存储库中的文件</font></font></a></li>
<li><a href="#verilog-module-parameters"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Verilog 模块参数</font></font></a></li>
<li><a href="#cycles-per-instruction-performance"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">每条指令的周期性能</font></font></a></li>
<li><a href="#picorv32-native-memory-interface"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 本机内存接口</font></font></a></li>
<li><a href="#pico-co-processor-interface-pcpi"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Pico 协处理器接口 (PCPI)</font></font></a></li>
<li><a href="#custom-instructions-for-irq-handling"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">IRQ 处理的自定义指令</font></font></a></li>
<li><a href="#building-a-pure-rv32i-toolchain"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建纯 RV32I 工具链</font></font></a></li>
<li><a href="#linking-binaries-with-newlib-for-picorv32"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将二进制文件与 PicoRV32 的 newlib 链接</font></font></a></li>
<li><a href="#evaluation-timing-and-utilization-on-xilinx-7-series-fpgas"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">评估：Xilinx 7 系列 FPGA 的时序和使用</font></font></a></li>
</ul>
<h2 tabindex="-1" dir="auto"><a id="user-content-features-and-typical-applications" class="anchor" aria-hidden="true" tabindex="-1" href="#features-and-typical-applications"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">特点和典型应用</font></font></h2>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">小型（7 系列 Xilinx 架构中的 750-2000 个 LUT）</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">高 f </font></font><sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">max</font></font></sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（7 系列 Xilinx FPGA 上为 250-450 MHz）</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可选本机内存接口或 AXI4-Lite 主接口</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可选的 IRQ 支持（使用简单的自定义 ISA）</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可选的协处理器接口</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该 CPU 旨在用作 FPGA 设计和 ASIC 中的辅助处理器。由于其高 f </font></font><sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">max，</font></font></sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">它可以集成到大多数现有设计中，而无需跨时钟域。当在较低频率下运行时，它将具有很大的时序裕度，因此可以在不影响时序收敛的情况下将其添加到设计中。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于更小的尺寸，可以禁用对寄存器</font></font><code>x16</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">..</font></font><code>x31</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以及</font></font><code>RDCYCLE[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>RDTIME[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>RDINSTRET[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的支持，从而将处理器变成 RV32E 内核。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此外，还可以在双端口和单端口寄存器文件实现之间进行选择。前者提供更好的性能，而后者则导致更小的核心。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：在专用存储器资源中实现寄存器文件的架构中，例如许多 FPGA，禁用 16 个高位寄存器和/或禁用双端口寄存器文件可能不会进一步减小内核大小。</font></font></em></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">核心存在三种变体：</font></font><code>picorv32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>picorv32_axi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>picorv32_wb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。第一个提供了简单的本机内存接口，易于在简单的环境中使用。</font></font><code>picorv32_axi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提供 AXI-4 Lite Master 接口，可轻松与已使用 AXI 标准的现有系统集成。</font></font><code>picorv32_wb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提供Wishbone主接口。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提供了一个单独的内核</font></font><code>picorv32_axi_adapter</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来桥接本机内存接口和 AXI4。该内核可用于创建自定义内核，其中包括一个或多个 PicoRV32 内核以及本地 RAM、ROM 和内存映射外设，使用本机接口相互通信，并通过 AXI4 与外界通信。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可选的 IRQ 功能可用于对来自外部的事件做出反应、实现故障处理程序或捕获来自更大 ISA 的指令并在软件中模拟它们。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可选的 Pico 协处理器接口 (PCPI) 可用于在外部协处理器中实现非分支指令。该软件包中</font></font><code>MUL[H[SU|U]]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含</font><font style="vertical-align: inherit;">实现 M 标准扩展指令的 PCPI 内核的实现
</font></font><code>DIV[U]/REM[U]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-files-in-this-repository" class="anchor" aria-hidden="true" tabindex="-1" href="#files-in-this-repository"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此存储库中的文件</font></font></h2>
<h4 tabindex="-1" dir="auto"><a id="user-content-readmemd" class="anchor" aria-hidden="true" tabindex="-1" href="#readmemd"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">自述文件.md</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">你现在正在读它。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-picorv32v" class="anchor" aria-hidden="true" tabindex="-1" href="#picorv32v"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">picorv32.v</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该 Verilog 文件包含以下 Verilog 模块：</font></font></p>
<table>
<thead>
<tr>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">模块</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">描述</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>picorv32</code></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 CPU</font></font></td>
</tr>
<tr>
<td><code>picorv32_axi</code></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">带 AXI4-Lite 接口的 CPU 版本</font></font></td>
</tr>
<tr>
<td><code>picorv32_axi_adapter</code></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从 PicoRV32 内存接口到 AXI4-Lite 的适配器</font></font></td>
</tr>
<tr>
<td><code>picorv32_wb</code></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">带Wishbone Master接口的CPU版本</font></font></td>
</tr>
<tr>
<td><code>picorv32_pcpi_mul</code></td>
<td><font style="vertical-align: inherit;"></font><code>MUL[H[SU|U]]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执行指令</font><font style="vertical-align: inherit;">的 PCPI 内核</font></font></td>
</tr>
<tr>
<td><code>picorv32_pcpi_fast_mul</code></td>
<td><font style="vertical-align: inherit;"></font><code>picorv32_pcpi_fast_mul</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用单周期乘法器</font><font style="vertical-align: inherit;">的版本</font></font></td>
</tr>
<tr>
<td><code>picorv32_pcpi_div</code></td>
<td><font style="vertical-align: inherit;"></font><code>DIV[U]/REM[U]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执行指令</font><font style="vertical-align: inherit;">的 PCPI 内核</font></font></td>
</tr>
</tbody>
</table>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">只需将此文件复制到您的项目中即可。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-makefile-and-testbenches" class="anchor" aria-hidden="true" tabindex="-1" href="#makefile-and-testbenches"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Makefile 和测试平台</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一个基本的测试环境。运行以</font><font style="vertical-align: inherit;">在标准配置下</font></font><code>make test</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">运行标准测试台 ( )。</font></font><code>testbench.v</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">还有其他测试台和配置。有关详细信息，</font><font style="vertical-align: inherit;">请参阅</font></font><code>test_*</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Makefile 中的 make 目标。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Run </font></font><code>make test_ez</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">to run</font></font><code>testbench_ez.v</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是一个非常简单的测试平台，不需要外部固件 .hex 文件。这在 RISC-V 编译器工具链不可用的环境中非常有用。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注：测试台使用 Icarus Verilog。然而，Icarus Verilog 0.9.7（撰写本文时的最新版本）有一些错误，导致测试平台无法运行。升级到最新的Icarus Verilog github master来运行测试台。</font></font></em></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-firmware" class="anchor" aria-hidden="true" tabindex="-1" href="#firmware"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">固件/</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一个简单的测试固件。这会运行一些 C 代码的基本测试</font></font><code>tests/</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，测试 IRQ 处理和乘法 PCPI 内核。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中的所有代码</font></font><code>firmware/</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">均属于公共领域。只需复制您可以使用的任何内容即可。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-tests" class="anchor" aria-hidden="true" tabindex="-1" href="#tests"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">测试/</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="https://github.com/riscv/riscv-tests"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来自riscv-tests</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的简单指令级测试</font><font style="vertical-align: inherit;">。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-dhrystone" class="anchor" aria-hidden="true" tabindex="-1" href="#dhrystone"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">水石/</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">另一个运行 Dhrystone 基准测试的简单测试固件。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-picosoc" class="anchor" aria-hidden="true" tabindex="-1" href="#picosoc"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">皮可索克/</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 PicoRV32 的简单示例 SoC，可以直接从内存映射 SPI 闪存执行代码。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-scripts" class="anchor" aria-hidden="true" tabindex="-1" href="#scripts"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">脚本/</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">适用于不同（综合）工具和硬件架构的各种脚本和示例。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-verilog-module-parameters" class="anchor" aria-hidden="true" tabindex="-1" href="#verilog-module-parameters"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Verilog 模块参数</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下 Verilog 模块参数可用于配置 PicoRV32 内核。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_counters-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_counters-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_COUNTERS（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此参数启用对</font></font><code>RDCYCLE[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>RDTIME[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和
</font></font><code>RDINSTRET[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的支持。如果</font></font><code>ENABLE_COUNTERS</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置为零，</font><font style="vertical-align: inherit;">该指令将导致硬件陷阱（与任何其他不受支持的指令一样） 。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：严格来说</font></font><code>RDCYCLE[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">， 、</font></font><code>RDTIME[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、 和</font></font><code>RDINSTRET[H]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
指令对于 RV32I 内核来说不是可选的。但在应用程序代码经过调试和分析后，它们很可能不会被错过。对于 RV32E 内核，此指令是可选的。</font></font></em></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_counters64-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_counters64-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_COUNTERS64（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此参数启用对</font></font><code>RDCYCLEH</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>RDTIMEH</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>RDINSTRETH</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
指令的支持。如果该参数设置为 0，则</font></font><code>ENABLE_COUNTERS</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置为 1，则只有</font></font><code>RDCYCLE</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>RDTIME</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、 和</font></font><code>RDINSTRET</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令可用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_regs_16_31-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_regs_16_31-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_REGS_16_31（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该</font><font style="vertical-align: inherit;">参数启用对寄存器的支持</font></font><code>x16</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">... </font></font><code>x31</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">RV32E ISA 不包括该寄存器。然而，当代码尝试访问该寄存器时，RV32E ISA 规范需要一个硬件陷阱。 PicoRV32 中未实现此功能。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_regs_dualport-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_regs_dualport-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_REGS_DUALPORT（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">寄存器堆可以用两个或一个读端口来实现。双端口寄存器文件可以稍微提高性能，但也可以增加内核的大小。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-latched_mem_rdata-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#latched_mem_rdata-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LATCHED_MEM_RDATA（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"></font><code>mem_rdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果交易后外部电路保持稳定，</font><font style="vertical-align: inherit;">则将其设置为 1 。</font><font style="vertical-align: inherit;">在默认配置中，PicoRV32 内核仅期望
</font></font><code>mem_rdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">输入在周期内有效，</font></font><code>mem_valid &amp;&amp; mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并在内部锁存该值。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该参数仅适用于核心</font></font><code>picorv32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。在
</font></font><code>picorv32_axi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">核心中</font></font><code>picorv32_wb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，它被隐式设置为 0。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-two_stage_shift-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#two_stage_shift-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TWO_STAGE_SHIFT（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">默认情况下，移位操作分两个阶段进行：首先以 4 位为单位进行移位，然后以 1 位为单位进行移位。这加快了轮班操作，但增加了额外的硬件。将此参数设置为0可禁用两级移位，以进一步减小内核的尺寸。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-barrel_shifter-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#barrel_shifter-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BARREL_SHIFTER（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">默认情况下，移位操作是通过连续少量移位来执行的（见</font></font><code>TWO_STAGE_SHIFT</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上文）。设置此选项后，将使用桶形移位器。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-two_cycle_compare-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#two_cycle_compare-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TWO_CYCLE_COMPARE（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通过添加额外的 FF 级，以向条件分支指令添加额外的时钟周期延迟为代价，稍微放宽了最长的数据路径。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：当在综合流程中启用重定时（又名“寄存器平衡”）时，启用此参数将最有效。</font></font></em></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-two_cycle_alu-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#two_cycle_alu-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TWO_CYCLE_ALU（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这在 ALU 数据路径中添加了一个额外的 FF 级，从而以使用 ALU 的所有指令的额外时钟周期为代价来改善时序。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：当在综合流程中启用重定时（又名“寄存器平衡”）时，启用此参数将最有效。</font></font></em></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-compressed_isa-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#compressed_isa-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">COMPRESSED_ISA（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这使得能够支持 RISC-V 压缩指令集。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-catch_misalign-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#catch_misalign-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CATCH_MISALIGN（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 0 可禁用捕获未对齐内存访问的电路。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-catch_illinsn-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#catch_illinsn-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CATCH_ILLINSN（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 0 可禁用捕获非法指令的电路。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将此选项设置为 0 时，内核仍会捕获</font></font><code>EBREAK</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令。启用 IRQ 后，an</font></font><code>EBREAK</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通常会触发 IRQ 1。此选项设置为 0 时，an</font></font><code>EBREAK</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将捕获处理器而不触发中断。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_pcpi-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_pcpi-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_PCPI（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 1 以启用 Pico 协处理器接口 (PCPI)。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_mul-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_mul-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_MUL（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该参数在内部启用 PCPI 并实例化</font></font><code>picorv32_pcpi_mul</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
实现</font></font><code>MUL[H[SU|U]]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的内核。仅当 ENABLE_PCPI 也被设置时，外部 PCPI 接口才起作用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_fast_mul-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_fast_mul-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_FAST_MUL（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该参数在内部启用 PCPI 并实例化</font></font><code>picorv32_pcpi_fast_mul</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
实现</font></font><code>MUL[H[SU|U]]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的内核。仅当 ENABLE_PCPI 也被设置时，外部 PCPI 接口才起作用。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果同时设置了 ENABLE_MUL 和 ENABLE_FAST_MUL，则 ENABLE_MUL 设置将被忽略，并且快速乘法器核心将被实例化。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_div-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_div-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_DIV（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该参数在内部启用 PCPI 并实例化</font></font><code>picorv32_pcpi_div</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
实现</font></font><code>DIV[U]/REM[U]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的内核。仅当 ENABLE_PCPI 也被设置时，外部 PCPI 接口才起作用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_irq-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_irq-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_IRQ（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 1 以启用 IRQ。 （有关 IRQ 的讨论，请参阅下面的“IRQ 处理的自定义指令”）</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_irq_qregs-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_irq_qregs-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_IRQ_QREGS（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 0 可禁用对</font></font><code>getq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>setq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的支持。如果没有 q 寄存器，IRQ 返回地址将存储在 x3 (gp) 中，IRQ 位掩码将存储在 x4 (tp) 中，根据 RISC-V ABI，全局指针和线程指针寄存器。从普通 C 代码生成的代码不会与这些寄存器交互。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当 ENABLE_IRQ 设置为 0 时，对 q 寄存器的支持始终被禁用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_irq_timer-default--1" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_irq_timer-default--1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_IRQ_TIMER（默认 = 1）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 0 以禁用对该</font></font><code>timer</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令的支持。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当 ENABLE_IRQ 设置为 0 时，对定时器的支持始终被禁用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-enable_trace-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#enable_trace-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ENABLE_TRACE（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"></font><code>trace_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用和输出端口</font><font style="vertical-align: inherit;">生成执行跟踪</font></font><code>trace_data</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。为了演示此功能，请运行</font></font><code>make test_vcd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建跟踪文件，然后运行</font></font><code>python3 showtrace.py testbench.trace firmware/firmware.elf</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对其进行解码。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-regs_init_zero-default--0" class="anchor" aria-hidden="true" tabindex="-1" href="#regs_init_zero-default--0"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REGS_INIT_ZERO（默认 = 0）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其设置为 1 可将所有寄存器初始化为零（使用 Verilog</font></font><code>initial</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">块）。这对于模拟或形式验证很有用。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-masked_irq-default--32h-0000_0000" class="anchor" aria-hidden="true" tabindex="-1" href="#masked_irq-default--32h-0000_0000"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">MASKED_IRQ（默认 = 32'h 0000_0000）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该位掩码中的 1 位对应于永久禁用的 IRQ。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-latched_irq-default--32h-ffff_ffff" class="anchor" aria-hidden="true" tabindex="-1" href="#latched_irq-default--32h-ffff_ffff"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LATCHED_IRQ（默认 = 32'h ffff_ffff）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该位掩码中的 1 位表示相应的 IRQ 被“锁定”，即当 IRQ 线仅在一个周期内为高电平时，中断将被标记为挂起并保持挂起状态，直到调用中断处理程序（又名“脉冲中断”）或“边沿触发中断”）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将此位掩码中的一位设置为 0，以将中断线转换为“电平敏感”中断。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-progaddr_reset-default--32h-0000_0000" class="anchor" aria-hidden="true" tabindex="-1" href="#progaddr_reset-default--32h-0000_0000"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PROGADDR_RESET（默认 = 32'h 0000_0000）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">程序的起始地址。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-progaddr_irq-default--32h-0000_0010" class="anchor" aria-hidden="true" tabindex="-1" href="#progaddr_irq-default--32h-0000_0010"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PROGADDR_IRQ（默认 = 32'h 0000_0010）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中断处理程序的起始地址。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-stackaddr-default--32h-ffff_ffff" class="anchor" aria-hidden="true" tabindex="-1" href="#stackaddr-default--32h-ffff_ffff"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">STACKADDR（默认 = 32'h ffff_ffff）</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当此参数的值不同于 0xffffffff 时，寄存器</font></font><code>x2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（堆栈指针）在复位时初始化为此值。 （所有其他寄存器保持未初始化状态。）请注意，RISC-V 调用约定要求堆栈指针在 16 字节边界上对齐（RV32I 软浮点调用约定为 4 字节）。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-cycles-per-instruction-performance" class="anchor" aria-hidden="true" tabindex="-1" href="#cycles-per-instruction-performance"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">每条指令的周期性能</font></font></h2>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">简短提醒：该核心针对尺寸和 f </font></font><sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">max</font></font></sub><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">进行了优化，而不是针对性能进行了优化。</font></font></em></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">除非另有说明，否则以下数字适用于 ENABLE_REGS_DUALPORT 处于活动状态并连接到可在一个时钟周期内容纳请求的存储器的 PicoRV32。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">每条指令的平均周期 (CPI) 约为 4，具体取决于代码中的指令组合。各个指令的 CPI 编号可在下表中找到。 “CPI (SP)”列包含未使用 ENABLE_REGS_DUALPORT 构建的内核的 CPI 编号。</font></font></p>
<table>
<thead>
<tr>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">操作说明</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">消费者物价指数</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">消费者物价指数（SP）</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">直接跳转 (jal)</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ALU 寄存器 + 立即数</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ALU 寄存器 + 寄存器</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">分支（未采取）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">内存负载</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">5</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">5</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">记忆库</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">5</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">6</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">分支（已拍摄）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">5</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">6</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">间接跳转（jalr）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">6</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">6</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">轮班操作</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4-14</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4-15</font></font></td>
</tr>
</tbody>
</table>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当</font></font><code>ENABLE_MUL</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">激活时，一条</font></font><code>MUL</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令将在 40 个周期内执行，一条</font></font><code>MULH[SU|U]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令将在 72 个周期内执行。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当</font></font><code>ENABLE_DIV</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">激活时，一条</font></font><code>DIV[U]/REM[U]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令将在 40 个周期内执行。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">激活后</font></font><code>BARREL_SHIFTER</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，移位操作所需的时间与任何其他 ALU 操作一样长。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下 dhrystone 基准测试结果适用于启用了
</font></font><code>ENABLE_FAST_MUL</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>ENABLE_DIV</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>BARREL_SHIFTER</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">选项的核心。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Dhrystone 基准测试结果：0.516 DMIPS/MHz（908 Dhrystones/秒/MHz）</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于 Dhrystone 基准，平均 CPI 为 4.100。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果不使用前瞻内存接口（通常需要最大时钟速度），结果会降至 0.305 DMIPS/MHz 和 5.232 CPI。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-picorv32-native-memory-interface" class="anchor" aria-hidden="true" tabindex="-1" href="#picorv32-native-memory-interface"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 本机内存接口</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 的本机内存接口是一种简单的有效就绪接口，一次可以运行一个内存传输：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>output        mem_valid
output        mem_instr
input         mem_ready

output [31:0] mem_addr
output [31:0] mem_wdata
output [ 3:0] mem_wstrb
input  [31:0] mem_rdata
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="output        mem_valid
output        mem_instr
input         mem_ready

output [31:0] mem_addr
output [31:0] mem_wdata
output [ 3:0] mem_wstrb
input  [31:0] mem_rdata" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">内核通过置位 来启动内存传输</font></font><code>mem_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。有效信号保持高电平，直到对等方断言</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。在此期间所有核心输出都很稳定</font></font><code>mem_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。如果内存传输是指令提取，则内核断言</font></font><code>mem_instr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-read-transfer" class="anchor" aria-hidden="true" tabindex="-1" href="#read-transfer"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">读取传输</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在读取传输中，</font></font><code>mem_wstrb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">值为 0 并且</font></font><code>mem_wdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">未使用。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存储器读取地址</font></font><code>mem_addr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并使读取的值在
</font></font><code>mem_rdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">周期为</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">高电平时可用。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不需要外部等待周期。存储器读取可以异步实现，并</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在与 相同的周期内变为高电平</font></font><code>mem_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，或者
</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">与常数 1 相关联。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-write-transfer" class="anchor" aria-hidden="true" tabindex="-1" href="#write-transfer"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">写传输</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在写入传输中</font></font><code>mem_wstrb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不为 0 并且</font></font><code>mem_rdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">未被使用。存储器将数据写入</font></font><code>mem_wdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">地址</font></font><code>mem_addr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并通过置位确认传输</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的 4 位</font></font><code>mem_wstrb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是寻址字中四个字节的写使能。只有</font></font><code>0000</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、 、</font></font><code>1111</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>1100</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>0011</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>1000</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>0100</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>0010</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font><font style="vertical-align: inherit;">8 个值</font></font><code>0001</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是可能的，即分别不写、写 32 位、写高 16 位、写低 16 位或写单个字节。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不需要外部等待周期。存储器可以立即确认写入，并</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在与 相同的周期内变为高电平
</font></font><code>mem_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，或者</font></font><code>mem_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">与常数 1 相关联。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-look-ahead-interface" class="anchor" aria-hidden="true" tabindex="-1" href="#look-ahead-interface"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">前瞻接口</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 内核还提供“前瞻存储器接口”，该接口比正常接口早一个时钟周期提供有关下一个存储器传输的所有信息。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>output        mem_la_read
output        mem_la_write
output [31:0] mem_la_addr
output [31:0] mem_la_wdata
output [ 3:0] mem_la_wstrb
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="output        mem_la_read
output        mem_la_write
output [31:0] mem_la_addr
output [31:0] mem_la_wdata
output [ 3:0] mem_la_wstrb" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在变高之前的时钟周期中</font></font><code>mem_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，该接口将在</font></font><code>mem_la_read</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或上输出一个脉冲</font></font><code>mem_la_write</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，以指示下一个时钟周期中读或写事务的开始。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注：信号</font></font><code>mem_la_read</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>mem_la_write</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、 和</font></font><code>mem_la_addr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">由 PicoRV32 内核内的组合电路驱动。使用前瞻接口可能比使用上述普通存储器接口更难实现时序收敛。</font></font></em></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-pico-co-processor-interface-pcpi" class="anchor" aria-hidden="true" tabindex="-1" href="#pico-co-processor-interface-pcpi"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Pico 协处理器接口 (PCPI)</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Pico 协处理器接口 (PCPI) 可用于在外部内核中实现非分支指令：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>output        pcpi_valid
output [31:0] pcpi_insn
output [31:0] pcpi_rs1
output [31:0] pcpi_rs2
input         pcpi_wr
input  [31:0] pcpi_rd
input         pcpi_wait
input         pcpi_ready
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="output        pcpi_valid
output [31:0] pcpi_insn
output [31:0] pcpi_rs1
output [31:0] pcpi_rs2
input         pcpi_wr
input  [31:0] pcpi_rd
input         pcpi_wait
input         pcpi_ready" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当遇到不支持的指令并且 PCPI 功能被激活（请参阅上面的 ENABLE_PCPI）时，然后</font></font><code>pcpi_valid</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">被断言，指令字本身在 上输出</font></font><code>pcpi_insn</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，</font></font><code>rs1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>rs2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
字段被解码，并且这些寄存器中的值在</font></font><code>pcpi_rs1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和上输出</font></font><code>pcpi_rs2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">然后，外部 PCPI 内核可以解码指令、执行指令，并
</font></font><code>pcpi_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在指令执行完成时断言。可以选择写入</font></font><code>pcpi_rd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并</font></font><code>pcpi_wr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">断言结果值。然后，PicoRV32 内核将对</font></font><code>rd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">指令字段进行解码，并将值写入</font></font><code>pcpi_rd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">相应的寄存器。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当 16 个时钟周期内没有外部 PCPI 内核确认该指令时，将引发非法指令异常并调用相应的中断处理程序。需要多个周期来执行指令的 PCPI 内核应</font></font><code>pcpi_wait</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在指令成功解码后立即断言，并保持断言直至其断言</font></font><code>pcpi_ready</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。这将防止 PicoRV32 内核引发非法指令异常。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-custom-instructions-for-irq-handling" class="anchor" aria-hidden="true" tabindex="-1" href="#custom-instructions-for-irq-handling"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">IRQ 处理的自定义指令</font></font></h2>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：PicoRV32 中的 IRQ 处理功能不遵循 RISC-V 特权 ISA 规范。相反，使用一小组非常简单的自定义指令以最小的硬件开销实现 IRQ 处理。</font></font></em></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">仅当通过参数启用 IRQ 时，才支持以下自定义指令</font></font><code>ENABLE_IRQ</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（见上文）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32 内核具有一个内置中断控制器，具有 32 个中断输入。可以通过</font></font><code>irq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
置位内核输入</font><font style="vertical-align: inherit;">中的相应位来触发中断。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当中断处理程序启动时，</font></font><code>eoi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">所处理中断的中断结束 (EOI) 信号变高。</font></font><code>eoi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当中断处理程序返回时，信号再次变低</font><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">IRQ 0-2 可以通过以下内置中断源在内部触发：</font></font></p>
<table>
<thead>
<tr>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中断请求</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中断源</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">定时器中断</font></font></td>
</tr>
<tr>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">EBREAK/ECALL 或非法指令</font></font></td>
</tr>
<tr>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">总线错误（未对齐内存访问）</font></font></td>
</tr>
</tbody>
</table>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该中断也可以由外部源触发，例如通过 PCPI 连接的协处理器。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">内核有 4 个额外的 32 位寄存器</font></font><code>q0 .. q3</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，用于 IRQ 处理。当调用 IRQ 处理程序时，寄存器</font></font><code>q0</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含返回地址以及</font></font><code>q1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要处理的所有 IRQ 的位掩码。这意味着当 中设置了多个位时，对中断处理程序的一次调用需要服务多个 IRQ </font></font><code>q1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当启用对压缩指令的支持时，当中断的指令是压缩指令时，q0 的 LSB 被设置。如果 IRQ 处理程序想要解码中断指令，则可以使用此方法。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">寄存器</font></font><code>q2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>q3</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">未初始化，可在 IRQ 处理程序中保存/恢复寄存器值时用作临时存储。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下所有指令均编码在</font></font><code>custom0</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">操作码下。所有这些指令中 f3 和 rs2 字段都被忽略。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font><a href="/YosysHQ/picorv32/blob/master/firmware/custom_ops.S"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">firmware/custom_ops.S</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，了解实现本指令助记符的GNU 汇编器宏。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">有关中断处理程序汇编器包装器的示例实现，</font><font style="vertical-align: inherit;">请参阅</font></font><a href="/YosysHQ/picorv32/blob/master/firmware/start.S"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">固件/start.S</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> ，有关实际中断处理程序的</font></font><a href="/YosysHQ/picorv32/blob/master/firmware/irq.c"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">固件/irq.c 。</font></font></a><font style="vertical-align: inherit;"></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-getq-rd-qs" class="anchor" aria-hidden="true" tabindex="-1" href="#getq-rd-qs"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">getq rd, qs</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该指令将值从 q 寄存器复制到通用寄存器。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000000 ----- 000XX --- XXXXX 0001011
f7      rs2   qs    f3  rd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000000 ----- 000XX --- XXXXX 0001011
f7      rs2   qs    f3  rd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>getq x5, q2
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="getq x5, q2" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h4 tabindex="-1" dir="auto"><a id="user-content-setq-qd-rs" class="anchor" aria-hidden="true" tabindex="-1" href="#setq-qd-rs"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">setq qd, rs</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该指令将值从通用寄存器复制到 q 寄存器。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000001 ----- XXXXX --- 000XX 0001011
f7      rs2   rs    f3  qd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000001 ----- XXXXX --- 000XX 0001011
f7      rs2   rs    f3  qd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>setq q2, x5
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="setq q2, x5" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h4 tabindex="-1" dir="auto"><a id="user-content-retirq" class="anchor" aria-hidden="true" tabindex="-1" href="#retirq"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">退出</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从中断中返回。该指令将值复制</font></font><code>q0</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
到程序计数器并重新启用中断。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000010 ----- 00000 --- 00000 0001011
f7      rs2   rs    f3  rd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000010 ----- 00000 --- 00000 0001011
f7      rs2   rs    f3  rd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>retirq
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="retirq" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h4 tabindex="-1" dir="auto"><a id="user-content-maskirq" class="anchor" aria-hidden="true" tabindex="-1" href="#maskirq"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">马斯基尔克</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“IRQ Mask”寄存器包含屏蔽（禁用）中断的位掩码。该指令将新值写入 irq 掩码寄存器并读取旧值。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000011 ----- XXXXX --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000011 ----- XXXXX --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>maskirq x1, x2
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="maskirq x1, x2" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">处理器在禁用所有中断的情况下启动。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当非法指令或总线错误中断被禁用时，非法指令或总线错误将导致处理器停止。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-waitirq" class="anchor" aria-hidden="true" tabindex="-1" href="#waitirq"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">等待</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">暂停执行，直到中断变为待处理状态。待处理 IRQ 的位掩码被写入</font></font><code>rd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000100 ----- 00000 --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000100 ----- 00000 --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>waitirq x1
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="waitirq x1" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h4 tabindex="-1" dir="auto"><a id="user-content-timer" class="anchor" aria-hidden="true" tabindex="-1" href="#timer"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">计时器</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将定时器计数器重置为新值。计数器对时钟周期进行倒计数，并在从 1 转换到 0 时触发定时器中断。将计数器设置为零会禁用定时器。计数器的旧值被写入
</font></font><code>rd</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>0000101 ----- XXXXX --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="0000101 ----- XXXXX --- XXXXX 0001011
f7      rs2   rs    f3  rd    opcode" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例子：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>timer x1, x2
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="timer x1, x2" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h2 tabindex="-1" dir="auto"><a id="user-content-building-a-pure-rv32i-toolchain" class="anchor" aria-hidden="true" tabindex="-1" href="#building-a-pure-rv32i-toolchain"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建纯 RV32I 工具链</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TL;DR：运行以下命令来构建完整的工具链：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>make download-tools
make -j$(nproc) build-tools
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="make download-tools
make -j$(nproc) build-tools" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="https://github.com/riscv/riscv-tools"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">riscv-tools</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建脚本中的默认设置</font><font style="vertical-align: inherit;">将构建可以针对任何 RISC-V ISA 的编译器、汇编器和链接器，但这些库是针对 RV32G 和 RV64G 目标构建的。按照以下说明构建针对纯 RV32I CPU 的完整工具链（包括库）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下命令将为纯 RV32I 目标构建 RISC-V GNU 工具链和库，并将其安装在</font></font><code>/opt/riscv32i</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code># Ubuntu packages needed:
sudo apt-get install autoconf automake autotools-dev curl libmpc-dev \
        libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo \
    gperf libtool patchutils bc zlib1g-dev git libexpat1-dev

sudo mkdir /opt/riscv32i
sudo chown $USER /opt/riscv32i

git clone https://github.com/riscv/riscv-gnu-toolchain riscv-gnu-toolchain-rv32i
cd riscv-gnu-toolchain-rv32i
git checkout 411d134
git submodule update --init --recursive

mkdir build; cd build
../configure --with-arch=rv32i --prefix=/opt/riscv32i
make -j$(nproc)
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="# Ubuntu packages needed:
sudo apt-get install autoconf automake autotools-dev curl libmpc-dev \
        libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo \
    gperf libtool patchutils bc zlib1g-dev git libexpat1-dev

sudo mkdir /opt/riscv32i
sudo chown $USER /opt/riscv32i

git clone https://github.com/riscv/riscv-gnu-toolchain riscv-gnu-toolchain-rv32i
cd riscv-gnu-toolchain-rv32i
git checkout 411d134
git submodule update --init --recursive

mkdir build; cd build
../configure --with-arch=rv32i --prefix=/opt/riscv32i
make -j$(nproc)" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这些命令都将使用 prefix 命名</font></font><code>riscv32-unknown-elf-</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，这样可以轻松地将它们与常规 riscv-tools 并排安装（</font></font><code>riscv64-unknown-elf-</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">默认情况下使用名称前缀）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或者，您可以简单地使用 PicoRV32 的 Makefile 中的以下 make 目标之一来构建</font></font><code>RV32I[M][C]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">工具链。您仍然需要安装所有先决条件，如上所述。然后在 PicoRV32 源目录中运行以下任意命令：</font></font></p>
<table>
<thead>
<tr>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">命令</font></font></th>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装目录</font></font></th>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ISA</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><code>make -j$(nproc) build-riscv32i-tools</code></td>
<td align="left"><code>/opt/riscv32i/</code></td>
<td align="left"><code>RV32I</code></td>
</tr>
<tr>
<td align="left"><code>make -j$(nproc) build-riscv32ic-tools</code></td>
<td align="left"><code>/opt/riscv32ic/</code></td>
<td align="left"><code>RV32IC</code></td>
</tr>
<tr>
<td align="left"><code>make -j$(nproc) build-riscv32im-tools</code></td>
<td align="left"><code>/opt/riscv32im/</code></td>
<td align="left"><code>RV32IM</code></td>
</tr>
<tr>
<td align="left"><code>make -j$(nproc) build-riscv32imc-tools</code></td>
<td align="left"><code>/opt/riscv32imc/</code></td>
<td align="left"><code>RV32IMC</code></td>
</tr>
</tbody>
</table>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或者只需运行即可</font></font><code>make -j$(nproc) build-tools</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建并安装所有四个工具链。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">默认情况下，调用任何这些 make 目标都会（重新）下载工具链源。</font><font style="vertical-align: inherit;">
提前</font><font style="vertical-align: inherit;">运行一次</font></font><code>make download-tools</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">下载源。</font></font><code>/var/cache/distfiles/</code><font style="vertical-align: inherit;"></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意：这些说明适用于 riscv-gnu-toolchain 的 git rev 411d134 (2018-02-14)。</font></font></em></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-linking-binaries-with-newlib-for-picorv32" class="anchor" aria-hidden="true" tabindex="-1" href="#linking-binaries-with-newlib-for-picorv32"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将二进制文件与 PicoRV32 的 newlib 链接</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">工具链（请参阅最后一节的安装说明）附带一个版本的 newlib C 标准库。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用链接器脚本</font></font><a href="/YosysHQ/picorv32/blob/master/firmware/riscv.ld"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">firmware/riscv.ld</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将二进制文件链接到newlib 库。使用此链接描述文件将创建一个入口点为 0x10000 的二进制文件。 （默认的链接器脚本没有静态入口点，因此需要一个适当的 ELF 加载器来在加载程序时确定运行时的入口点。）</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Newlib 附带了一些系统调用存根。您需要提供您自己的这些系统调用的实现，并将您的程序与此实现链接起来，覆盖 newlib 中的默认存根。请参阅</font><a href="/YosysHQ/picorv32/blob/master/scripts/cxxdemo"><font style="vertical-align: inherit;">scripts/cxxdemo/</font></a></font><code>syscalls.c</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中的</font><font style="vertical-align: inherit;">
示例来了解如何执行此操作。</font></font><a href="/YosysHQ/picorv32/blob/master/scripts/cxxdemo"><font style="vertical-align: inherit;"></font></a><font style="vertical-align: inherit;"></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-evaluation-timing-and-utilization-on-xilinx-7-series-fpgas" class="anchor" aria-hidden="true" tabindex="-1" href="#evaluation-timing-and-utilization-on-xilinx-7-series-fpgas"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">评估：Xilinx 7 系列 FPGA 的时序和使用</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下评估是使用 Vivado 2017.3 进行的。</font></font></p>
<h4 tabindex="-1" dir="auto"><a id="user-content-timing-on-xilinx-7-series-fpgas" class="anchor" aria-hidden="true" tabindex="-1" href="#timing-on-xilinx-7-series-fpgas"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx 7 系列 FPGA 的时序</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"></font><code>picorv32_axi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">已启用的模块</font><font style="vertical-align: inherit;">已</font></font><code>TWO_CYCLE_ALU</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">针对所有速度等级的 Xilinx Artix-7T、Kintex-7T、Virtex-7T、Kintex UltraScale 和 Virtex UltraScale 器件进行布局和布线。二分搜索用于查找设计满足时序的最短时钟周期。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font><code>make table.txt</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">script </font></font><a href="/YosysHQ/picorv32/blob/master/scripts/vivado"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/vivado/</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<table>
<thead>
<tr>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设备</font></font></th>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设备</font></font></th>
<th align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">速度等级</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">时钟周期（频率）</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Kintex-7T</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xc7k70t-fbg676-2</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.4 纳秒（416 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Kintex-7T</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xc7k70t-fbg676-3</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.2 纳秒（454 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Virtex-7T</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xc7v585t-ffg1761-2</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.3 纳秒（434 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Virtex-7T</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xc7v585t-ffg1761-3</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.2 纳秒（454 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Kintex UltraScale</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcku035-fbva676-2-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.0 纳秒（500 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Kintex UltraScale</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcku035-fbva676-3-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.8 纳秒（555 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Virtex UltraScale</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcvu065-ffvc1517-2-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.1 纳秒（476 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛灵思 Virtex UltraScale</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcvu065-ffvc1517-3-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.0 纳秒（500 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Kintex UltraScale+</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcku3p-ffva676-2-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.4 纳秒（714 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Kintex UltraScale+</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcku3p-ffva676-3-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.3 纳秒（769 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Virtex UltraScale+</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcvu3p-ffvc1517-2-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-2</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.5 纳秒（666 兆赫）</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx Virtex UltraScale+</font></font></td>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xcvu3p-ffvc1517-3-e</font></font></td>
<td align="center"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-3</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.4 纳秒（714 兆赫）</font></font></td>
</tr>
</tbody>
</table>
<h4 tabindex="-1" dir="auto"><a id="user-content-utilization-on-xilinx-7-series-fpgas" class="anchor" aria-hidden="true" tabindex="-1" href="#utilization-on-xilinx-7-series-fpgas"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xilinx 7 系列 FPGA 上的使用</font></font></h4>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">下表列出了以下三个核心在区域优化综合中的资源利用率：</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（小）：</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该</font></font><code>picorv32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">模块没有计数器指令，没有两级移位，具有外部锁存</font></font><code>mem_rdata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，并且不捕获未对齐的内存访问和非法指令。</font></font></p>
</li>
<li>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（常规）：</font></font></strong><font style="vertical-align: inherit;"></font><code>picorv32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">处于默认配置的模块</font><font style="vertical-align: inherit;">。</font></font></p>
</li>
<li>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（大）：</font></font></strong><font style="vertical-align: inherit;"></font><code>picorv32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">启用了 PCPI、IRQ、MUL、DIV、BARREL_SHIFTER 和 COMPRESSED_ISA 功能的模块</font><font style="vertical-align: inherit;">。</font></font></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font><code>make area</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">script </font></font><a href="/YosysHQ/picorv32/blob/master/scripts/vivado"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/vivado/</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<table>
<thead>
<tr>
<th align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">核心变体</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">切片 LUT</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LUT 作为内存</font></font></th>
<th align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">切片寄存器</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（小）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第761章</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">48</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第442章</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（常规）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">917</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">48</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第583章</font></font></td>
</tr>
<tr>
<td align="left"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PicoRV32（大）</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2019年</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">88</font></font></td>
<td align="right"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1085</font></font></td>
</tr>
</tbody>
</table>
</article></div>
