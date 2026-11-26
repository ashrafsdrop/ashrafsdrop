# Ashraful Islam (@ashrafsdrop)

Low-level systems and graphics programmer specializing in virtualization runtimes, emulator internals, GPU architecture translation, and memory management.

---

### Core Technical Focus

- **GPU Architecture & Shader Translation:**
  - Emulation of AMD RDNA2 / GCN ISA to Direct3D 12 (DXIL / DXBC).
  - SIMD wave control flow: Wave32 / Wave64 semantics, vector condition code (\VCC\) whole-wave branching, \EXEC\ lane-masking, and waterfall loops.
  - Structurisation, SSA reconstruction, dead-code elimination, and register-pressure bounding for shader compilation pipelines.

- **Virtual Memory & Shadowing Engines:**
  - High-performance HLE memory management: physical page recycling, memory aliasing, and custom kernel allocators (\XMem\).
  - Copy-back GPU shadow memory synchronization: per-page dirty tracking, atomic snapshotting, and serialized remap invalidation.
  - Non-reentrant lock discipline and lock-free thread synchronization.

- **Systems Architecture & Low-Level Tooling:**
  - Native Windows / Linux kernel-level interfaces, high-concurrency dispatch, and asynchronous I/O architectures (\DStorage\).
  - Hardware-level validation across NVIDIA GeForce (RTX 30/40/50 series), AMD Radeon (RDNA2/RDNA3), and Microsoft WARP software rasterizers.

---

### Technical Proficiencies

- **Languages:** Rust, C++, C, Assembly (x86-64, AMD RDNA2 ISA), HLSL.
- **Graphics & Systems APIs:** DirectX 12 / D3D12, DXIL Bitcode, Win32 / NT API.
- **Tools & Infrastructure:** Git, LLVM / DXC Compiler Infrastructure, Software WARP, D3D12 Debug Layer & InfoQueue.

---

### Key Open-Source Engineering (VIctory Runtime)

Core contributions to **[VIctory](https://github.com/Marvisak/VIctory)**, a high-performance console virtualization runtime written in Rust:

- **GPU Memory Watch & Shadow Engine:** Implemented serialized copy-back synchronization against concurrent memory remapping, eliminating stale writeback hazards on dynamically mapped guest pages ([#2612](https://github.com/Marvisak/VIctory/pull/2612)).
- **Shader Compiler Core:** Re-engineered wave-wide \s_cbranch_vccz\ / \s_cbranch_vccnz\ branching to evaluate raw \VCC\ without \EXEC\ masking across Wave32 / Wave64 targets, preserving graphics fallback invariants across the 24,850 retail shader census ([#2405](https://github.com/Marvisak/VIctory/pull/2405)).
- **Memory Management Subsystem:** Authored physical page recycling for \XMem\ allocations, preventing address fragmentation under high alloc/free churn ([#1935](https://github.com/Marvisak/VIctory/pull/1935)).
- **Instruction Lowering:** Resolved independent dword alignment truncation for multi-term buffer loads ([#1939](https://github.com/Marvisak/VIctory/pull/1939)) and lane-op bypass mechanics ([#1312](https://github.com/Marvisak/VIctory/pull/1312)).

---

### Connect

- **GitHub:** [@ashrafsdrop](https://github.com/ashrafsdrop)
- **Email:** \waker11752@gmail.com