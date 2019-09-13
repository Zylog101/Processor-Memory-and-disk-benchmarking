# Processor-Memory-and-Disk-Benchmarking

This project aims to benchmark different parts of a computer system, such as the CPU, memory and disk

Language used: C

Abstractions: PThreads

Infrastructure: Chameleon testbed (https://www.chameleoncloud.org)

KVM virtual machine m1.medium (2 virtual processors with 4GB RAM and 40GB disk)

OS: CentOS 7 Linux


**Individual benchmark description**
* CPU (11 experiments):
  * For CPU benchmarks, strong scaling experiments are performed; this means that the amount of work (e.g. number of instructions you want to run in your benchmark) is set, and the amount of work per thread is reduced as the number of threads increase
  *  The processor speed, in terms of double precision floating point operations per second (Giga FLOPS, 109 FLOPS) and integer operations per second (Giga IOPS, 109 IOPS) is measured
  *  The processor speed is measured at varying levels of concurrency (1 thread, 2 threads, 4 threads, 8 threads)
  *  Theoretical peak performance of processor in flops/sec is calculated
  * Linpack benchmark (http://en.wikipedia.org/wiki/LINPACK) is used to compare theoretical results and our custom benchmark results
  
* Memory (61 experiments):
  *  For memory benchmarks, strong scaling experiments are performed
  *  parameter space includes read+write operations (e.g. memcpy), sequential write access (e.g. memset), random write access, varying block sizes (8B, 8KB, 8MB, 80MB), and varying the concurrency (1 thread, 2 threads, 4 threads, and 8 threads);
  *  Metrics used for measuring are throughput (Megabytes per second, MB/sec) and latency (microseconds, us);
  *  Varying the number of threads optimal number of concurrency to get the best performance is found aswell
  *  Theoretical memory bandwidth of memory, based on the type of memory and the speed is computed
  *  Stream benchmark (http://www.cs.virginia.edu/stream/) is used to compare theoretical results and our custom benchmark results
  
* Disk (49 experiments):
  *  For disk benchmarks, strong scaling experiments are performed
  *  The disk speed is measured
  *  Parameter space includes read+write operations, sequential read access, random read access, varying block sizes (8B, 8KB, 8MB, 80MB), and varying the concurrency (1 thread, 2 threads, 4 threads, 8 threads)
  *  Metrics used for measuring are throughput (MB/sec) and latency (ms);
  *  The optimal number of concurrency to get the best performance is inferred
  *  IOZone benchmark (http://www.iozone.org/) is used to compare theoretical results and our custom benchmark results
