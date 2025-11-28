---
theme: default
highlighter: shiki
lineNumbers: false
transition: fade
css: unocss
fonts:
  sans: 'Inter'
  serif: 'Source Han Sans'
---

<style>
/* 字体引入 */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Source+Han+Sans:wght@400;700;900&display=swap');
/* 基础字号下调一档 */
html { font-size: 18px; }

/* 标题字号同步缩小 */
.font-super { font-size: 3.5rem; line-height: 1.1; } /* 封面主标题 */
.font-sub   { font-size: 1.75rem; line-height: 1.2; } /* 封面副标题 */
.font-title.text-6xl { font-size: 3rem; }            /* 各页大标题 */

/* 正文半粗 */
body, p, li {
  font-family: 'Inter', sans-serif;
  font-weight: 600;
}

/* 卡片文字：再小一点 + 自动换行 */
.card-text {
  font-size: 1rem;                /* 16px */
  line-height: 1.5;
  overflow-wrap: break-word;
  word-break: break-word;
}
</style>

<!-- 1️⃣ 封面 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title font-super text-[#c0392b]">
    源来如此 | 上游资讯
  </div>
  <div v-motion :initial="{ opacity:0 }" :enter="{ opacity:1,transition:{delay:500,duration:800} }"
       class="font-sub text-[#7f8c8d] mt-4">
    2025.11.17 - 2025.11.23
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:1000} }"
       class="mt-16 px-10 py-4 border-2 border-[#2e5984] rounded-full bg-[#f8f6f0]/80 text-[#2e5984] font-bold text-xl">
    Linux Kernel | QEMU | Rust | RISC-V
  </div>
</div>

---

<!-- 2️⃣ 本周概览 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    本周概览
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 max-w-5xl grid grid-cols-2 gap-6 text-lg">
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border-l-4 border-[#c0392b] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl">RISC-V 服务器平台</div>
      <p class="card-text text-[#7f8c8d] mt-2">引入 RVSP-ref 参考板与 WorldGuard 安全扩展</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border-l-4 border-[#2e5984] text-left cursor-pointer shadow-sm">
      <div class="text-[#2e5984] font-bold text-xl">图形与显示优化</div>
      <p class="card-text text-[#7f8c8d] mt-2">VirtIO-GPU 支持 VFIO DMABUF，提升直通性能</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border-l-4 border-[#7f8c8d] text-left cursor-pointer shadow-sm">
      <div class="text-[#7f8c8d] font-bold text-xl">存储设备修复</div>
      <p class="card-text text-[#7f8c8d] mt-2">SD 卡擦除优化、NVMe PMR 验证、Block 竞争修复</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border-l-4 border-[#c0392b] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl">稳定版更新</div>
      <p class="card-text text-[#7f8c8d] mt-2">v10.0.7, v10.1.3, v7.2.22 进入发布前冻结期</p>
    </div>
  </div>
</div>

---

<!-- 3️⃣ RISC-V 重大更新 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    RISC-V 架构重大更新
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 max-w-4xl space-y-4 text-xl text-left text-[#222]">
    <p><span class="text-[#c0392b] font-bold">1. 服务器参考板 (RVSP-ref)</span> – 基于 virt 机器，去除 virtio-mmio 等非标设备，支持 PCIe 和 AIA。</p>
    <p><span class="text-[#c0392b] font-bold">2. WorldGuard 安全扩展</span> – 硬件隔离机制，新增 wgChecker 设备和全局配置。</p>
    <p><span class="text-[#c0392b] font-bold">3. KVM 修复</span> – 修复 env->priv 设置，解决 GDB 物理地址解析错误。</p>
  </div>
</div>

---

<!-- 4️⃣ 显卡与显示 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    显卡与显示优化
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 max-w-5xl grid grid-cols-2 gap-8 text-lg">
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl mb-2">VFIO DMABUF 支持</div>
      <p class="card-text text-[#7f8c8d]">为 VirtIO-GPU 引入对 VFIO 设备（如直通 dGPU）的支持，利用 VFIO_DEVICE_FEATURE_DMA_BUF 实现高效显存共享。</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-6 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl mb-2">代码清理与修复</div>
      <ul class="list-disc pl-4 card-text text-[#7f8c8d] space-y-1">
        <li>统一 virtio_gpu_create_mapping_iov 错误检查逻辑</li>
        <li>修复资源创建中的错误处理 Bug</li>
      </ul>
    </div>
  </div>
</div>

---

<!-- 5️⃣ 存储与块设备 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    存储与块设备
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 max-w-6xl grid grid-cols-3 gap-6 text-lg">
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl mb-2">SD 卡优化</div>
      <p class="card-text text-[#7f8c8d]">擦除操作改为填充 0（原为 1），修正 SCR 寄存器位，提升性能并允许块设备优化。</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#2e5984] font-bold text-xl mb-2">NVMe 修复</div>
      <p class="card-text text-[#7f8c8d]">增加对 PMR（持久内存区域）大小的验证，确保其至少为 16 字节，符合 PCI 规范。</p>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#7f8c8d] font-bold text-xl mb-2">Block Backend</div>
      <p class="card-text text-[#7f8c8d]">修复了在恢复排队请求时可能发生的竞争条件，防止断言失败。</p>
    </div>
  </div>
</div>

---

<!-- 6️⃣ 版本发布 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    版本发布与稳定版维护
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 flex gap-8 text-xl">
    <div class="px-8 py-5 bg-[#f8f6f0] border-2 border-[#c0392b] rounded-lg shadow-sm">
      <span class="text-[#c0392b] font-bold text-2xl">v10.2</span>
      <span class="ml-4 text-[#7f8c8d]">RC2 Fixes</span>
    </div>
    <div class="px-8 py-5 bg-[#f8f6f0] border-2 border-[#2e5984] rounded-lg shadow-sm">
      <span class="text-[#2e5984] font-bold text-2xl">Frozen</span>
      <span class="ml-4 text-[#7f8c8d] text-base">v10.0.7<br>v10.1.3<br>v7.2.22</span>
    </div>
  </div>
  <div v-motion :initial="{ y:20,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:800} }"
       class="mt-8 text-base bg-[#f8f6f0] border border-[#dcd5c7] px-4 py-2 rounded">Freeze Date: 2025-12-01</div>
</div>

---

<!-- 7️⃣ 架构特定更新 -->
<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    架构特定更新
  </div>
  <div v-motion :initial="{ y:50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{delay:500} }"
       class="mt-12 max-w-6xl grid grid-cols-3 gap-6 text-lg">
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#c0392b] font-bold text-xl mb-2">ARM</div>
      <ul class="text-base space-y-2 text-[#7f8c8d] list-disc pl-4">
        <li>SMMUv3: 引入 banked registers，为 TrustZone 做准备。</li>
        <li>ASPEED: PCIe Root Port 启用 MSI 支持热插拔。</li>
      </ul>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#2e5984] font-bold text-xl mb-2">x86</div>
      <ul class="text-base space-y-2 text-[#7f8c8d] list-disc pl-4">
        <li>清理: 移除 isapc 中无用的 Xen 代码。</li>
        <li>文档: 增加 Intel Diamond Rapids CPU 模型说明。</li>
      </ul>
    </div>
    <div v-motion :initial="{ scale:1 }" :hover="{ scale:1.03 }" :transition="{ type:'spring', stiffness:300 }"
         class="p-5 bg-[#f8f6f0]/90 rounded-xl border border-[#dcd5c7] text-left cursor-pointer shadow-sm">
      <div class="text-[#7f8c8d] font-bold text-xl mb-2">WHPX</div>
      <ul class="text-base space-y-2 text-[#7f8c8d] list-disc pl-4">
        <li>内存管理: 重构逻辑，支持中断控制器，适配 EDK2。</li>
      </ul>
    </div>
  </div>
</div>

---

<!-- 8️⃣ 封底 -->

<div class="absolute inset-0 bg-[#f5f2e8]"/>
<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iZ3JpZCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjUwIiBwYXR0ZXJuVW5pdHM9InVzZXJTcGFjZU9uVXNlIj48cGF0aCBkPSJNIDUwIDAgMCAwIDAgNTAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2RjZDVjNyIgc3Ryb2tlLXdpZHRoPSIwLjUiIG9wYWNpdHk9IjAuMyIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9InVybCgjZ3JpZCkiLz48L3N2Zz4=')] opacity-40"/>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-[#222]">
  <div v-motion :initial="{ y:-50,opacity:0 }" :enter="{ y:0,opacity:1,transition:{duration:800} }"
       class="font-title text-6xl text-[#c0392b]">
    源来如此 | 欢迎三连关注
  </div>
  <div v-motion :initial="{ opacity:0 }" :enter="{ opacity:1,transition:{delay:500,duration:800} }"
       class="font-sub text-[#7f8c8d] mt-4">
    QEMU Weekly Update | 2025.11.17 - 11.23
  </div>
  <div v-motion :initial="{ opacity:0 }" :enter="{ opacity:1,transition:{delay:1500,duration:800} }"
       class="mt-12 text-center text-[#7f8c8d]">
    <p class="text-xl mb-2">感谢各位开发者本周的贡献！</p>
    <p class="text-lg">本期贡献：张三、李四、王五、赵六</p>
  </div>
</div>

<!-- 全局动画 -->
<style>
.grid-bg { animation: gridBreath 8s ease-in-out infinite; }
@keyframes gridBreath {
  0%,100% { opacity: 0.2; }
  50% { opacity: 0.4; }
}
</style>