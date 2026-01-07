# GeoPhys Core
### High-Performance Spatial Physics & LiDAR Integration

**GeoPhys Core** is an R&D project bridging cinematic physics simulation with geospatial mobile technology. It implements a **Position Based Dynamics (PBD)** solver in C++20 to run real-time natural phenomena simulations (cloth, fluid, particles) on unstructured 3D meshes captured via mobile LiDAR.

---

## 🎯 Project Intent
This project demonstrates a "Hybrid" skill set tailored for:
* **VFX R&D:** High-performance C++, numerical stability, and geometry processing.
* **Google Geo:** Swift/iOS expertise, large-scale spatial data, and accessibility-first design.

---

## 🛠 Tech Stack

| Layer | Technologies |
| :--- | :--- |
| **Simulation Core** | C++20, Eigen, SIMD (NEON/AVX), OpenVDB |
| **Mobile Frontend** | Swift, SwiftUI, ARKit (LiDAR), Metal |
| **Interoperability** | Swift-C++ Interop (Zero-copy), Protobufs |
| **Engineering Ops** | CMake, GoogleTest, GitHub Actions (CI/CD) |



---

## ✨ Key Features

* **PBD Solver:** Custom-built C++ simulation engine for stable, real-time cloth and fluid dynamics.
* **Spatial Hash Grid:** $O(1)$ collision detection for massive point clouds/meshes.
* **Zero-Copy Bridge:** Direct pointer passing from ARKit vertex buffers to C++ kernels.
* **Performance Optimized:** Multi-threaded execution via Intel TBB and ARM NEON intrinsics.
* **USD Pipeline:** Export simulation data as `.usdz` for industry-standard VFX tools.
* **Accessible UI:** Haptic feedback and VoiceOver support for 3D spatial awareness.

---

## 🏗 High-Level Architecture

The system follows a modular design to ensure the physics core remains platform-independent.

1.  **Ingestion:** LiDAR sensor captures environment geometry.
2.  **Processing:** Custom Bounding Volume Hierarchy (BVH) organizes mesh data.
3.  **Simulation:** PBD Solver resolves particle-mesh constraints.
4.  **Feedback:** Metal-accelerated rendering and iOS haptic responses.



---

## 🚀 Quick Start (C++ Core)

```bash
mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)
./tests/run_benchmarks
