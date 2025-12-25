# PX_TRIAGE

PX-TRIAGE is a containerized portworx troubleshooting tools. All tools are now consolidated into a single image for ease of use.

## Getting Started

To build the docker image, clone this repo and run the build script. Docker must be running on your system.

### Build the Triage Image
```bash
./bin/build
```

## Available Tools
The single `sens/triage` image contains the following tools:
- `etcdctl`
- `fio`
- `ioping`
- `iostat`
- `mpstat`
- `sed`

## Repository Structure
See [docs/architecture.md](docs/architecture.md) for a detailed overview of the project structure.

## EXAMPLES:

### ETCDCTL Commands:
```bash
docker run --rm -e ETCDCTL_API=3 sens/triage etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" member list -w table
```

### FIO Commands:
```bash
docker run --rm -it -v myvol:/mnt sens/triage fio --blocksize=64k --filename=/mnt/fio.dat --ioengine=libaio --readwrite=write --size=10G --name=test --direct=1 --iodepth=128 --end_fsync=1
```

### IOPING Commands:
```bash
docker run --rm -it -v myvol:/mnt sens/triage ioping -D /mnt
```

### IOSTAT Commands:
```bash
docker run --rm sens/triage iostat -xm 1
```

### MPSTAT Commands:
```bash
docker run --rm sens/triage mpstat -xm 1
```
