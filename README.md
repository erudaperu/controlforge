# ControlForge

**A C++ workspace for exploring a self-balancing pendulum.**

ControlForge is at its foundation milestone: a minimal CMake project and executable entry point are in place. The next stage is to turn that foundation into a pendulum simulation and feedback-control experiment.

**Stack:** C++20 · CMake · optional Ninja

## Current milestone

| Area | State |
| --- | --- |
| Build configuration | CMake target for the C++ executable |
| Entry point | Startup message and successful exit |
| Pendulum dynamics | Planned |
| Numerical integration | Planned |
| Feedback controller | Planned |

## Build and run

Use a C++20-capable compiler and CMake 3.12 or newer. Ninja is optional; omit `-G Ninja` to use your configured default generator.

```sh
cmake -S . -B build -G Ninja
cmake --build build
./build/controlforge
```

Expected output:

```text
ControlForge started successfully.
```

A direct Linux build is also possible:

```sh
mkdir -p build
g++ -std=c++20 -O2 -Wall -Wextra -pedantic src/main.cpp -o build/controlforge
./build/controlforge
```

## Source map

- [`src/main.cpp`](src/main.cpp) — executable entry point.
- [`CMakeLists.txt`](CMakeLists.txt) — target and language-standard configuration.

## Development direction

Start with a documented pendulum model, add a fixed-step simulation, then introduce feedback control and comparisons between controlled and uncontrolled motion. Tests should follow those behaviours as they are implemented.

The current entry point compiled and ran with GCC 14.2.0 on Linux on November 11, 2026, without compiler warnings. CMake was unavailable in that validation environment, so its build path was not executed.

