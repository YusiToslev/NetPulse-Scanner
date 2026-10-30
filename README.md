# NetPulse-Scanner

## Short Description
NetPulse Scanner is a concurrent .NET application that audits network infrastructure by testing multiple host and port connections simultaneously using parallel worker threads.

## What One Job Is
A single job consists of performing a connection test (TCP/Ping) on one specific host and port combination.

## Planned Features
- **Configurable Workers:** Support for 4 or 8 parallel workers processing jobs from a shared queue.
- **Controls:** Master Start, Stop, Pause, and Resume buttons for thread management.
- **Worker Monitor:** Live UI view showing what each worker thread is currently scanning.
- **Results Table:** Clean tabular layout displaying host name, port, status (Online/Offline), and response time.
- **Responsive UI:** Thread-safe architecture ensuring the application never freezes.

## Shared Data & Concurrency Protection
- **Shared Job Queue:** Contains pending host targets. Protected by a `lock` when workers pull new jobs.
- **Shared Results List:** Stores completed scan outcomes. Protected by a `lock` when workers append new results to avoid race conditions.
