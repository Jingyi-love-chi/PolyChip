# PolyChip

PolyChip is a chiplet-oriented framework for Domain Specific Architecture, built on RISC-V and designed for scalable multi-die integration in high-performance computing and machine learning accelerators.

## Project Overview

PolyChip provides an end-to-end toolchain for chiplet RTL design, die-to-die interconnect modeling, simulation, and software development—from individual tile implementation to multi-die system-level verification. The framework uses a modular chiplet architecture with flexible composition and extension, supporting diverse 2.5D/3D packaging and specialized compute integration scenarios.

## Quick Start

### Installation in Nix
We use Nix Flake as our main build system. If you have not installed nix, install it following the [guide](https://nix.dev/manual/nix/2.28/installation/installing-binary.html), and enable flake following the [wiki](https://nixos.wiki/wiki/Flakes#Enable_flakes). Or you can try the [installer](https://github.com/DeterminateSystems/nix-installer) provided by Determinate Systems, which enables flake by default.


**1. Clone Repository**

```bash
git clone https://github.com/DangoSys/ploychip.git
```

**2. Initialize Environment**
```bash
cd buckyball
./scripts/nix/build-all.sh
```

After the first time installation, you can enter the environment anytime by running:

```bash
nix develop
```

**3. Verify Installation**

Run Verilator simulation test to verify installation:

```bash
bbdev verilator --run '--jobs 16 --binary ctest_vecunit_matmul_ones_singlecore-baremetal --config sims.verilator.BuckyballToyVerilatorConfig --batch'
```

