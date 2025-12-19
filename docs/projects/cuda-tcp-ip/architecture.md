# Architecture

This page explains the *conceptual* data path. Keep it high-level so it stays accurate as the code evolves.

## Data path

1. **Client** connects to the TCP server and sends fixed-size messages.
2. **Server** uses `epoll` to multiplex many sockets efficiently.
3. On each message:
   - receive payload into a host buffer
   - copy to GPU memory
   - run a small CUDA kernel (“tiny transform”)
   - copy result back to host
   - send response

## Design goals

- Make the network loop and GPU work visible and measurable.
- Keep the CUDA kernel intentionally small so you can focus on:
  - memory copies
  - batching opportunities
  - socket throughput and latency

## Next upgrades (good for README + future docs)

- Add an optional “batching” mode (N messages → 1 kernel launch).
- Add pinned memory (`cudaHostAlloc`) option.
- Add zero-copy experiments (where supported).
- Add a “CPU-only” mode as a baseline.
