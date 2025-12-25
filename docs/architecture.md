# Repository Architecture

The `px-triage` repository is organized to manage a consolidated containerized troubleshooting tool called `triage`.

## Structure

```
px-triage/
├── bin/                # Executable scripts
│   └── build           # Build script for the triage image
├── docs/               # Extended documentation
│   └── architecture.md # This file
├── source/             # Tool source code
│   └── triage/         # Consolidated tool logic
│       └── Dockerfile  # Single Dockerfile for all tools
└── README.md           # Project entry point and examples
```

## Build System
The `bin/build` script builds the `sens/triage` image which contains all the troubleshooting tools.
Usage: `./bin/build`

## Included Tools
- `etcdctl`: ETCD client for cluster state inspection.
- `fio`: Flexible I/O tester for storage benchmarking.
- `ioping`: Real-time disk latency monitoring.
- `iostat`: CPU and I/O statistics.
- `mpstat`: Processor related statistics.
- `sed`: Stream editor for text processing.
