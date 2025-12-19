# Benchmarking

## Quick benchmark

Run server and client locally (see **Build & Run**), then vary:

- payload bytes (e.g. 256, 1024, 4096, 16384)
- exchanges (e.g. 10k, 100k)
- number of concurrent clients (multiple terminals)

Record:

- exchanges/sec (fps)
- CPU usage
- GPU utilization and memory throughput

## Suggested table to capture results

| Payload (B) | Clients | Exchanges | fps | Notes |
|---:|---:|---:|---:|---|
| 4096 | 1 | 100000 |  |  |
| 4096 | 4 | 100000 |  |  |

## Repro tips

- Pin CPU frequency governor if you care about stable numbers.
- Use `nvidia-smi` to confirm GPU clocks and utilization.
- Build in `Release`.
