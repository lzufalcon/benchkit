# Benchkit

A developer-centric toolkit module for Android to facilitate in-depth profiling and
benchmarking.

This module uses the Unity Installer template, which means that it can be installed
irrespective of the root solution you are using — it will install as a Magisk module
when possible, otherwise it will fall back to installing into `/system` directly.

CPU architectures other than AArch64 are **NOT** supported! There are no plans to
support them at this time.

## Contents

Command-line utilities:

- [callbench](https://github.com/kdrag0n/callbench) (`callbench`):
  A program to measure the speed of simple time syscalls and vDSO calls, as well as
  basic file I/O using both `mmap(2)` and `read(2)`
- [cyclictest](https://git.kernel.org/pub/scm/utils/rt-tests/rt-tests.git/tree/src/cyclictest/cyclictest.c?h=stable/devel/v1.0.1) (`cyclictest`):
  A program to measure timer expiration delay, useful for real-time latency testing
- [Dhrystone](https://github.com/ARM-software/workload-automation/blob/e387e3d9b79e936b50e5985c369aad1654cc9c06/wa/workloads/dhrystone/src/dhrystone.c) (`dhrystone`):
  A simple CPU integer performance benchmark typically used for calculating CPU
  capacities for an EAS energy model
- [Flexible I/O Tester](https://github.com/axboe/fio/tree/4e8c82b4e9804c52bf2c78327cc5bfca9d8aedfc) (`fio`):
  A flexible generic I/O tester that can simulate a variety of configurable workloads,
  created by Linux block subsystem maintainer [Jens Axboe](https://github.com/axboe)
- [GTcycles](https://github.com/kdrag0n/gtcycles) (`gtcycles`):
  A tool to measure the frequency of the CPU's generic timer
- [Hackbench](https://git.kernel.org/pub/scm/utils/rt-tests/rt-tests.git/tree/src/hackbench/hackbench.c?h=stable/devel/v1.0.1&id=34caa080e0472cf480f2e90538aaf300f9ae487b) (`hackbench`):
  A scheduler wakeup latency and pipe benchmark
- [IOzone](http://www.iozone.org/) (`iozone`):
  A general filesystem and I/O benchmark
- [memcpy](https://github.com/ARM-software/workload-automation/blob/e387e3d9b79e936b50e5985c369aad1654cc9c06/wa/workloads/memcpy/src/memcopy.c) (`memcpy`):
  A simple memory bandwidth tester that uses the `memcpy(3)` function from libc
- [perf](https://github.com/kdrag0n/proton_bluecross/tree/a9c87582ba82f2ec3889a975bd5e827d846676cd/tools/perf) (`perf`):
  The Linux kernel's native profiling tool that can be used for both the kernel and
  userspace applications, which also offers some built-in microbenchmarks accessible
  via `perf bench` (kernel 4.9 version)
- [rt-app](https://github.com/scheduler-tools/rt-app) (`rt-app`):
  A flexible real-time application simulator designed to replicate typical mobile
  workloads in a reproducible manner. Some reference tests (courtesy of ARM's
  Workload Automation project) are available in `/system/etc/rt-app`.
- [schbench](https://github.com/kdrag0n/schbench/blob/8d075b39d6a4cbb362b24912eddcdd362bf09649/schbench.c) (`schbench`):
  A minimal and detailed scheduler wakeup latency benchmark by Facebook
- [SLABtop](https://gitlab.com/procps-ng/procps/blob/2e7f38707a1fa5949ccf3655fa33a90c8b8a2ffc/slabtop.c) (`slabtop`):
  A tool to show kernel SLAB memory usage details (requires `CONFIG_SLUB_DEBUG=y` in
  kernel)
- [stress-ng](https://kernel.ubuntu.com/git/cking/stress-ng.git/) (`stress-ng`):
  A program to stress-test various hardware and kernel subsystems
- [sysbench](https://github.com/akopytov/sysbench) (`sysbench`):
  A scriptable database and system performance benchmark with several built-in scripts
- [hyperfine](https://github.com/sharkdp/hyperfine) (`hyperfine`):
  An advanced benchmark runner that makes it easy to run benchmarks in a
  statistically sound manner and export results into machine-readable formats

Android apps:

- [JankBench](https://android.googlesource.com/platform/frameworks/base/+/android-9.0.0_r47/tests/JankBench) (Benchmark):
  [joshuous](https://github.com/joshuous/)' modified version of Google's AOSP app for
  automating some tests from UIBench in a reproducible manner
- [TouchLatency](https://android.googlesource.com/platform/frameworks/base/+/refs/tags/android-9.0.0_r47/tests/TouchLatency/) (TouchLatency):
  Google's AOSP app for testing touch latency as well as frame rendering times and
  missed frames
- [UIBench](https://android.googlesource.com/platform/frameworks/base/+/refs/tags/android-9.0.0_r47/tests/UiBench/) (UiBench):
  Google's AOSP app for testing various mobile workloads and UI rendering tasks
- [Audio Latency Test](https://superpowered.com/latency) (Latency Test):
  Superpowered's app for testing end-to-end (i.e. speaker to microphone) audio latency

All native executables have been stripped of symbols and DWARF debug info to reduce size.
For Android apps, the visible launcher name is shown in parantheses.

## Links

- [**Donate** to show your support](https://paypal.me/dragon5232)
- [Module **GitHub** repository](https://github.com/kdrag0n/benchkit)

## Credits

- ARM for creating [LISA](https://github.com/ARM-software/lisa) and [Workload Automation](https://github.com/ARM-software/workload-automation), from which many of the executables were sourced
- [celtare21](https://github.com/celtare21) for the [IOzone](http://www.iozone.org/) executable
- [Zackptg5](https://github.com/Zackptg5) for the [Unity Installer template](https://github.com/Zackptg5/Unity)
- The creators of all the programs contained in this module
