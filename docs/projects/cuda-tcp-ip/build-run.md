# Build & Run

## Prerequisites

- Linux (the server uses `epoll`)
- NVIDIA GPU with CUDA support (this project targets `sm_50` style GPUs)
- CUDA Toolkit installed and `nvcc` available
- CMake + Ninja recommended

## Build

From the project root:

```bash
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
cmake --build build -j
```

(From the repo README.)

If you need to force the CUDA architecture:

```bash
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_CUDA_ARCHITECTURES=50
cmake --build build -j
```

## Run (example)

### Terminal 1 — server

```bash
./build/bin/cc50_server 9099 4096
```

### Terminal 2 — client

```bash
./build/bin/cc50_client 127.0.0.1 9099 4096 1000
```

Where the arguments typically mean:

1. server host (client only)
2. TCP port
3. message/payload size (bytes)
4. number of request/response “exchanges” (client only)

## Expected output (example)

You should see the server print connection events, and the client print a throughput summary, e.g. `Completed ... exchanges ... fps`.
