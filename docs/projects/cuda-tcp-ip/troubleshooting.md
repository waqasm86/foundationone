# Troubleshooting

## `nvcc` not found / CUDA not detected

- Confirm CUDA Toolkit install and `nvcc --version`.
- Ensure CMake sees CUDA:

```bash
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_CUDA_COMPILER=$(which nvcc)
```

## Wrong GPU architecture

If you see `no kernel image is available for execution on the device`, rebuild with the correct arch:

```bash
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_CUDA_ARCHITECTURES=50
cmake --build build -j
```

## Permission / port issues

- Use a non-privileged port (>1024) like `9099`.
- Check if something else is listening:

```bash
ss -lntp | grep 9099
```

## `epoll` build issues on non-Linux

This project is Linux-focused because it uses `epoll`.
If you want portability later, consider abstracting the event loop (e.g., `poll`, `kqueue`, IOCP).
