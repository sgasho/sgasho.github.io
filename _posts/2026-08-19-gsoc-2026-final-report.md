---
title: "(WIP) - GSoC 2026 Final Report: Bringing Autodiff and Offload into Rust CI"
date: 2026-08-20 00:00:00 +0900
categories: [GSoC, Rust]
tags: [gsoc, rustc, autodiff, offload, ci]
---

- Contributor: [Shota Sugano](https://github.com/sgasho)
- Mentor: [Manuel Drehwald](https://github.com/ZuseZ4)
- Project: [Bringing autodiff and offload into Rust CI](https://summerofcode.withgoogle.com/programs/2026/projects/Wg1mCCHL)
- Organization: [The Rust Foundation](https://summerofcode.withgoogle.com/programs/2026/organizations/the-rust-foundation)

## Overview

The goal of this project was to bring Rust's automatic differentiation (std::autodiff) and GPU offloading support (std::offload) under CI coverage and into nightly distribution.

Before GSoC began, the status was:

* std::autodiff
    * partially supported in CI
        * built on Linux and on one Windows distribution runner, but not on macOS runners
        * no test coverage
* std::offload
    * no test coverage or nightly distribution in CI

Distributing and testing these two components in CI enables

* end users to use these features more easily
* us to catch regressions earlier, and to make future development and maintanance easier

## std::autodiff

### Distributing

Related PRs:

* (Before GSoC) [feat: dlopen Enzyme](https://github.com/rust-lang/rust/pull/149271)
* (Before GSoC) [cmake: make Enzyme Apple dynamic_lookup opt-in](https://github.com/EnzymeAD/Enzyme/pull/2670) (EnzymeAD/Enzyme)
* (Before GSoC) [Move aarch64-apple dist builder to dynamic llvm linking and enable autodiff in CI for it](https://github.com/rust-lang/rust/pull/152768/changes/c033de932ec6f46ccb1fd14bf848aec0bc88eece)
* (Before GSoC) [Link LLVM dynamically on aarch64-apple-darwin](https://github.com/rust-lang/rust/pull/151063)
* [Enable Enzyme for aarch64-apple-darwin](https://github.com/rust-lang/rust/pull/157240)
* [Update autodiff installation guide](https://github.com/rust-lang/rustc-dev-guide/pull/2896) (rustc-dev-guide)
* [Fix tablegen path in cross builds](https://github.com/EnzymeAD/Enzyme/pull/2856) (EnzymeAD/Enzyme)
* [Link LLVM dynamically on x86_64-apple](https://github.com/rust-lang/rust/pull/157557)
* [Add autodiff support for x86_64 apple darwin](https://github.com/rust-lang/rustc-dev-guide/pull/2920) (rustc-dev-guide)

### Testing

Related PR:

* [ci: Enable autodiff tests on x86_64 linux](https://github.com/rust-lang/rust/pull/157776)


## std::offload

### Distributing

Related PRs:

* [dlopen offload](https://github.com/rust-lang/rust/pull/160335)
* [Add offload support to the dist-x86_64-linux CI job](https://github.com/rust-lang/rust/pull/159064)
* [Add offload component on nightly](https://github.com/rust-lang/rust/pull/160991)

### Testing

Related PR:

* [ci: Enable offload tests in CI](https://github.com/rust-lang/rust/pull/158817)

## Current Status

## Future Work

## Acknowledgements


