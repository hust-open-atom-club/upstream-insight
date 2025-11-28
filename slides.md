---
# 主题设置
theme: seriph
# 背景图
background: https://source.unsplash.com/collection/94734566/1920x1080
# 语法高亮主题
highlighter: shiki
# 代码行号
lineNumbers: false
# 幻灯片信息
info: |
  ## QEMU Weekly Update
  2025-11-17 to 2025-11-23
# 绘图与动效配置
drawings:
  persist: false
transition: fade # 全局默认淡入淡出切屏
css: unocss
---

<!-- 封面页 -->
<div class="absolute top-0 left-0 w-full h-full bg-gradient-to-br from-blue-900 to-black opacity-90 z-0"></div>

<div class="relative z-10 h-full flex flex-col justify-center items-center text-center text-white">
  <div
    v-motion
    :initial="{ y: -50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { duration: 800 } }"
    class="text-6xl font-bold mb-4"
  >
    源来如此 | 上游资讯
  </div>
  
  <div
    v-motion
    :initial="{ opacity: 0 }"
    :enter="{ opacity: 1, transition: { delay: 500, duration: 800 } }"
    class="text-2xl text-blue-300 font-mono"
  >
    2025.11.17 - 2025.11.23
  </div>

  <div
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1000 } }"
    class="mt-12 px-6 py-2 border border-white/30 rounded-full backdrop-blur-sm"
  >
    Linux Kernel | QEMU | Rust | RISC-V
  </div>
</div>

---
layout: default
transition: fade # 页面切屏：淡入淡出
---

# 本周概览

<div class="grid grid-cols-2 gap-4 mt-8">
  <div 
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 100 } }"
    class="p-4 bg-gray-100 rounded-lg shadow-md border-l-4 border-blue-500 hover:scale-105 transition-transform duration-300"
  >
    <div class="text-xl font-bold text-blue-700 mb-2">RISC-V 服务器平台</div>
    <p class="text-sm text-gray-600">引入 RVSP-ref 参考板与 WorldGuard 安全扩展</p>
  </div>

  <div 
    v-motion
    :initial="{ x: 50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 200 } }"
    class="p-4 bg-gray-100 rounded-lg shadow-md border-l-4 border-green-500 hover:scale-105 transition-transform duration-300"
  >
    <div class="text-xl font-bold text-green-700 mb-2">图形与显示优化</div>
    <p class="text-sm text-gray-600">VirtIO-GPU 支持 VFIO DMABUF，提升直通性能</p>
  </div>

  <div 
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 300 } }"
    class="p-4 bg-gray-100 rounded-lg shadow-md border-l-4 border-purple-500 hover:scale-105 transition-transform duration-300"
  >
    <div class="text-xl font-bold text-purple-700 mb-2">稳定版冻结</div>
    <p class="text-sm text-gray-600">v10.0.7, v10.1.3, v7.2.22 进入发布前冻结期</p>
  </div>

  <div 
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 400 } }"
    class="p-4 bg-gray-100 rounded-lg shadow-md border-l-4 border-orange-500 hover:scale-105 transition-transform duration-300"
  >
    <div class="text-xl font-bold text-orange-700 mb-2">ARM & Windows</div>
    <p class="text-sm text-gray-600">WHPX 内存管理重构，支持 EDK2 在 Windows 上运行</p>
  </div>
</div>

---
layout: two-cols
transition: fade # 页面切屏：淡入淡出
---

# RISC-V 架构进展

<div class="mt-4 space-y-6">
  <div 
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 100 } }"
  >
    <h3 class="text-blue-600 font-bold">1. 服务器参考板 (RVSP-ref)</h3>
    <p class="text-sm opacity-80">基于 virt 机器，去除 virtio-mmio 等非标设备，支持 PCIe 和 AIA。</p>
  </div>

  <div 
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 200 } }"
  >
    <h3 class="text-blue-600 font-bold">2. WorldGuard 安全扩展</h3>
    <p class="text-sm opacity-80">硬件隔离机制，新增 wgChecker 设备和全局配置。</p>
  </div>

  <div 
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 300 } }"
  >
    <h3 class="text-blue-600 font-bold">3. KVM 修复</h3>
    <p class="text-sm opacity-80">修复 env->priv 设置，解决 GDB 物理地址解析错误。</p>
  </div>
</div>

::right::

<div 
  v-motion
  :initial="{ scale: 0.9, opacity: 0 }"
  :enter="{ scale: 1, opacity: 1, transition: { delay: 500 } }"
  class="ml-4 mt-16 p-4 bg-black rounded-lg shadow-2xl text-xs font-mono text-green-400 overflow-hidden"
>
  <div class="mb-2 border-b border-gray-700 pb-2 text-gray-400">Relevant Patches:</div>
  
  <div 
    v-motion
    :initial="{ x: 100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 600 } }"
    class="mb-3"
  >
  [PATCH v4 3/5] hw/riscv: experimental server platform reference machine
  </div>
  
  <div 
    v-motion
    :initial="{ x: 100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 700 } }"
    class="mb-3"
  >
  [PATCH v3 14/18] hw/misc: riscv_wgchecker: Implement RISC-V WorldGuard Checker
  </div>
  
  <div 
    v-motion
    :initial="{ x: 100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 800 } }"
  >
  [Stable-10.0.7] target/riscv/kvm: fix env->priv setting
  </div>
</div>

---
transition: fade # 页面切屏：淡入淡出
---

# 图形与显示 (VirtIO-GPU & VFIO)

<div class="flex items-center justify-between mt-8">
  
  <!-- Card 1 -->
  <div
    v-motion
    :initial="{ scale: 0.8, opacity: 0, rotate: -5 }"
    :enter="{ scale: 1, opacity: 1, rotate: 0, transition: { duration: 500 } }"
    class="w-[48%] bg-white p-6 rounded-xl shadow-lg border border-gray-200"
  >
    <div class="text-3xl mb-4">🎮</div>
    <h3 class="text-xl font-bold mb-2">VFIO DMABUF 支持</h3>
    <p class="text-sm text-gray-600 leading-relaxed">
      为 VirtIO-GPU 引入对 VFIO 设备（如直通 dGPU）的支持。
      <br><br>
      <span class="bg-blue-100 text-blue-800 px-2 py-1 rounded text-xs">Key Feature</span>
      利用 <code>VFIO_DEVICE_FEATURE_DMA_BUF</code> 实现高效显存共享。
    </p>
  </div>

  <!-- Card 2 -->
  <div
    v-motion
    :initial="{ scale: 0.8, opacity: 0, rotate: 5 }"
    :enter="{ scale: 1, opacity: 1, rotate: 0, transition: { delay: 200, duration: 500 } }"
    class="w-[48%] bg-white p-6 rounded-xl shadow-lg border border-gray-200"
  >
    <div class="text-3xl mb-4">🛠️</div>
    <h3 class="text-xl font-bold mb-2">代码清理与修复</h3>
    <ul class="list-disc pl-4 text-sm text-gray-600 space-y-2">
      <li>统一 <code>virtio_gpu_create_mapping_iov</code> 错误检查逻辑</li>
      <li>修复资源创建中的错误处理 Bug</li>
    </ul>
  </div>

</div>

---
layout: center
class: text-center
transition: fade # 页面切屏：淡入淡出
---

# 稳定版维护 (Stable Releases)
<div 
  v-motion
  :initial="{ y: 20, opacity: 0 }"
  :enter="{ y: 0, opacity: 1, transition: { delay: 200 } }"
  class="text-gray-500 mb-8"
>维护者 Michael Tokarev 密集推送修复</div>

<div class="flex justify-center gap-8">
  <div 
    v-motion
    :initial="{ scale: 0.9, opacity: 0 }"
    :enter="{ scale: 1, opacity: 1, transition: { delay: 300 } }"
    class="relative group"
  >
    <div class="absolute -inset-0.5 bg-gradient-to-r from-pink-600 to-purple-600 rounded-lg blur opacity-75 group-hover:opacity-100 transition duration-1000 group-hover:duration-200 animate-tilt"></div>
    <div class="relative px-7 py-4 bg-white rounded-lg leading-none flex items-center divide-x divide-gray-600">
      <span class="flex items-center space-x-5">
        <span class="pr-6 text-gray-900 font-bold text-xl">v10.2</span>
      </span>
      <span class="pl-6 text-indigo-400 group-hover:text-gray-900 transition duration-200">RC2 Fixes</span>
    </div>
  </div>

  <div 
    v-motion
    :initial="{ scale: 0.9, opacity: 0 }"
    :enter="{ scale: 1, opacity: 1, transition: { delay: 400 } }"
    class="relative group"
  >
    <div class="absolute -inset-0.5 bg-gradient-to-r from-blue-600 to-cyan-600 rounded-lg blur opacity-75 group-hover:opacity-100 transition duration-1000 group-hover:duration-200 animate-tilt"></div>
    <div class="relative px-7 py-4 bg-white rounded-lg leading-none flex items-center divide-x divide-gray-600">
      <span class="flex items-center space-x-5">
        <span class="pr-6 text-gray-900 font-bold text-xl">Frozen ❄️</span>
      </span>
      <span class="pl-6 text-blue-600 group-hover:text-gray-900 transition duration-200 text-sm">
        v10.0.7<br>v10.1.3<br>v7.2.22
      </span>
    </div>
  </div>
</div>

<div 
  v-motion
  :initial="{ y: 20, opacity: 0 }"
  :enter="{ y: 0, opacity: 1, transition: { delay: 500 } }"
  class="mt-8 text-sm bg-gray-100 p-2 rounded inline-block"
>
  📅 Freeze Date: 2025-12-01
</div>

---
transition: fade # 页面切屏：淡入淡出
---

# 存储、ARM 与其他更新

<div class="grid grid-cols-3 gap-4 mt-4">
  
  <!-- Col 1: Storage -->
  <div 
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 100 } }"
    class="bg-orange-50 p-4 rounded-lg"
  >
    <h3 class="font-bold text-orange-600 border-b border-orange-200 pb-2 mb-2">💾 存储设备</h3>
    <ul class="text-xs space-y-2">
      <li><strong>SD Card:</strong> 擦除操作填充 0 (原为 1)，修正 SCR 寄存器位。</li>
      <li><strong>NVMe:</strong> 强制 PMR 大小 >= 16 字节 (PCI 规范)。</li>
      <li><strong>Block:</strong> 修复恢复排队请求时的竞争条件。</li>
    </ul>
  </div>

  <!-- Col 2: ARM/WHPX -->
  <div 
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 200 } }"
    class="bg-blue-50 p-4 rounded-lg"
  >
    <h3 class="font-bold text-blue-600 border-b border-blue-200 pb-2 mb-2">🦾 ARM & WHPX</h3>
    <ul class="text-xs space-y-2">
      <li><strong>WHPX:</strong> 重构内存逻辑，支持中断控制器，适配 EDK2。</li>
      <li><strong>SMMUv3:</strong> 引入 banked registers，为 TrustZone 做准备。</li>
      <li><strong>ASPEED:</strong> PCIe Root Port 启用 MSI 支持热插拔。</li>
    </ul>
  </div>

  <!-- Col 3: Misc -->
  <div 
    v-motion
    :initial="{ y: 50, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 300 } }"
    class="bg-purple-50 p-4 rounded-lg"
  >
    <h3 class="font-bold text-purple-600 border-b border-purple-200 pb-2 mb-2">🧩 迁移与杂项</h3>
    <ul class="text-xs space-y-2">
      <li><strong>COLO:</strong> 修复 precopy 到 COLO 的状态转换错误。</li>
      <li><strong>x86:</strong> 移除 isapc 中无用的 Xen 代码。</li>
      <li><strong>pvpanic:</strong> 新增 PCI 接口支持。</li>
    </ul>
  </div>

</div>

---
layout: end
transition: fade # 页面切屏：淡入淡出
---

# Thank You

<div 
  v-motion
  :initial="{ opacity: 0, y: 20 }"
  :enter="{ opacity: 1, y: 0, transition: { duration: 500 } }"
  class="text-center"
>
  <p class="text-xl text-gray-600">QEMU Community Updates</p>
  <p class="text-3xl font-bold text-gray-800 mt-2">Nov 2025</p>
</div>

<div 
  v-motion
  :initial="{ opacity: 0 }"
  :enter="{ opacity: 1, transition: { delay: 300, duration: 800 } }"
  class="mt-10 text-center"
>
  <div class="inline-block px-6 py-3 bg-blue-500 text-white rounded-full shadow-lg">
    持续关注上游动态
  </div>
</div>