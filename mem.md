# Memory mappings

- `sudo cat /proc/iomem` - memory mapping of peripheral's address space (Registers) to real address space.
- `pmap -x <pid>` - map of a virtual memory address space of a process.

# Page faults

- `top` - shows the number of minor and major page faults, as well as deltas 
          between screen updates (`-d ss.t` - tenths of seconds precision).
- `ps` - `ps -o min_flt,maj_flt,cmd <pid>` - per process.
- `/usr/bin/time -v ./prog` - per process.
- `sar` - `sar -B 1 10` - system-level statistics only.

# Memory usage

- `free -h`

# Kernel buffers and page cache

- `free -h` - show how much memory is taken by kernel buffers and the page cache (`buff/cache`).
- `sync` - synchronize cached writes to disk.
- `sudo sh -c 'echo 1 >/proc/sys/vm/drop_caches'` - drop caches
  + alternative form: `sudo sysctl vm.drop_caches=1`
  + `1` - free page cache 
  + `2` - free dentries and inodes
  + `3` - free page cache, dentries and inodes 
- `fincore` from `linux-ftools` - can show which files are cached.

## swap

- `sudo swapoff -a`
- `sudo swapon -a`
- `free -h` - displays memory taken by swap (total/free/used).
- `top` - displays memory taken by swap (total/free/used)
