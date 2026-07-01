# Gredis - A High-Performance Redis Clone from Scratch in Go

Gredis is a high-performance, in-memory key-value storage engine (NoSQL database) built entirely from scratch using Golang. This project implements the Redis Serialization Protocol (RESP), advanced concurrency handling, and memory optimization to achieve a throughput of tens of thousands of requests per second.

The project strictly follows core system design principles and idiomatic Go practices to ensure a clean, maintainable, and highly efficient codebase.

---

## 🚀 Core Features

- **RESP Protocol Compliant:** Features a custom-built network parser for the Redis Serialization Protocol (supporting Bulk Strings, Simple Strings, Arrays, and Errors). It is 100% compatible with the official `redis-cli`.
- **High-Concurrency Architecture:** Leverages the power of **Goroutines** to handle thousands of concurrent TCP connections asynchronously. Each connected client is managed by a lightweight, independent thread of execution.
- **Thread-Safe In-Memory Data Structure:** Utilizes a highly optimized hash map protected by a `sync.RWMutex` (Read-Write Lock) to guarantee complete protection against *Data Races* during intensive concurrent read/write operations.
- **Efficient Resource Management:** Implements precise idiomatic Go error handling and the `defer` keyword to reliably release network sockets and reclaim system resources under any failure condition.
