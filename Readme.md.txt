# Win32 Native Task Orchestrator Engine (C++)

A high-performance, multi-threaded task orchestrator built purely on native Windows API primitives (`windows.h`). Designed to run on modern Windows without external dependencies or compiler POSIX threading requirements.

## Key Features
- **Priority Max-Heap Scheduling:** Ensures high-priority workloads execute first.
- **DAG Dependency Graph & Deadlock Prevention:** Detects circular dependencies automatically before scheduling.
- **Dynamic Thread Pool Scaling:** Scales worker threads up during workload spikes and scales idle threads down after timeouts.
- **Thread-Safe Futures (`TaskFuture<T>`):** Lightweight promise/future mechanism implemented natively with Win32 Events.
- **Dual-Lock Telemetry:** Fine-grained critical sections to separate queue mutations from real-time system profiling.
- **Robust Exception Safety:** Catches unhandled exceptions inside tasks without crashing worker threads.

## Build & Run
Compiled using GCC/MinGW on Windows:
```bash
g++ -O2 main.cpp -o orchestrator.exe
./orchestrator.exe