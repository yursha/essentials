# Memory mappings

- `sudo cat /proc/iomem` - memory mapping of peripheral's address space (Registers) to real address space.
- `pmap -x <pid>` - map of a virtual memory address space of a process.

# Page faults

- `top` - shows the number of minor and major page faults, as well as deltas 
          between screen updates (`-d ss.t` - tenths of seconds precision).
- `ps` - `ps -o min_flt,maj_flt,cmd <pid>` - per process.
- `/usr/bin/time -v ./prog` - per process.
- `sar` - `sar -B 1 10` - system-level statistics only.
