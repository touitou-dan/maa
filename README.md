Dynamic data structures, such as linked lists and search trees, have many advantages over static data structures: they are economical in memory consumption, provide fast insertion and deletion mechanisms, and can be resized efficiently.

However, some dynamic data structures have a major drawback: they hinder the processor's ability to speculate on future memory load instructions that could be executed in parallel. This lack of concurrency is especially problematic in very large dynamic data structures, where most pointer accesses result in high-latency external memory access.

Memory access amortization is a method that aims to facilitate speculative execution by interleaving the execution of multiple operations in a single thread, thereby increasing the number of independent memory accesses that can be executed in parallel.

list_array.c provides an example demonstrating how interleaving linked list scans can accelerate performance by a factor of ten on AWS's Graviton 3 processors. Please note that compilation optimizations further improve speculative execution potential. It is recommended to compile with -O3.
