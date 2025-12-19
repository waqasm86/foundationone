# CUDA TCP/IP

> C++20 + CUDA (sm_50) + epoll TCP server that runs a tiny GPU transform per message.

Repository: https://github.com/waqasm86/cuda-tcp-ip

## What this project demonstrates

- High-throughput TCP request/response loop using Linux `epoll`
- Moving data from the network → GPU → back to the network
- A simple performance harness to measure “exchanges per second” (fps)

## Binaries (typical)

Depending on your build configuration, you’ll usually see executables like:

- `cc50_server` — TCP server
- `cc50_client` — client load generator
- `cc50_lab` — combined harness / demo runner

(If the names differ in your current code, map these docs to your actual targets.)
