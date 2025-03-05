# memory-tools-systemtap
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://github.com/yvoinov/memory-tools-systemtap/blob/master/LICENSE)

## SystemTap memory tracing and profiling tools

Instrumentation scripts are prepared for tracing and profiling process allocation functions.

To use, copy the scripts and grant execute permissions.

To perform tracing or profiling, call the script using the process ID as an argument and let it run for a while.

The scripts run as an infinite loop until interrupted. Scripts print results upon interruption.

Example:
```sh
# profile-calloc.stp 88843
stap profile-malloc.stp 88843
Tracing allocations for PID 88843
Collecting data... press Ctrl-C to stop.
^C
Memory Allocation Stats for PID 88843:
malloc(64): 1680
malloc(512): 672
malloc(1024): 168
malloc(65536): 168
```
**Note**: You will have to edit the full path to the libc library specified as a macro.