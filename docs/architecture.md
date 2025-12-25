# Repository Architecture

The `px-triage` repository is organized to follow a domain-driven structure, making it easy to manage multiple containerized tools.

## Structure

```
px-triage/
├── bin/                # Executable scripts
│   └── build           # Universal build script
├── docs/               # Extended documentation
│   └── architecture.md # This file
├── source/             # Tool-specific source code
│   ├── etcdctl/
│   │   └── Dockerfile
│   ├── fio/
│   │   └── Dockerfile
│   ├── ...
└── README.md           # Project entry point and examples
```

## Build System
The `bin/build` script iterates through the `source/` directory and builds Docker images for each tool found.
Usage: `./bin/build [tool_name]`
