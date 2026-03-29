# OnePlus 9 Pro (lemonadep) Stock Kernel Build

## Phase 1: Custom Stock Kernel
This repository automates the compilation of a stock-matching custom kernel for the OnePlus 9 Pro running Android 14 (OxygenOS 14). It solves the challenges of generic kernel image (GKI) architecture on legacy SM8350 platforms.

### Key Features
- **Strict Parity:** Employs the required branch (`oneplus/sm8350_u_14.0.0_oneplus9`) to match the OEM release.
- **Dual-Repository Integration:** Automatically clones and directly merges the proprietary Qualcomm Out-of-Tree (OOT) modules and Techpacks to ensure perfect driver compilation.
- **Signature Bypass:** Utilizes modified `lahaina-qgki_defconfig` with `CONFIG_MODULE_SIG` disabled, preventing the custom kernel from rejecting proprietary OnePlus modules on boot.
- **LLVM Optimizer:** Forces LLVM=1 natively with AOSP Clang `r383902b` toolchain as recommended.
- **Space Optimization:** Aggressively clears unnecessary GitHub runner software (like .NET and Haskell) to provide the 15+ GBs of space required during the massive linking phase.

## Usage
Simply navigate to the **Actions** tab -> **Build OnePlus 9 Pro Custom Kernel (SM8350)** -> **Run workflow**. 
When complete, download the `Compiled-Kernel-SM8350` artifact containing your `Image` and device tree blobs.
