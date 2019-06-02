Bug report for --incompatible_use_specific_tool_files

Results of `bazel build :lib --incompatible_use_specific_tool_files`

```
Starting local Bazel server and connecting to it...
INFO: Analyzed target //:lib (12 packages loaded, 122 targets configured).
INFO: Found 1 target...
INFO: Deleting stale sandbox base /private/var/tmp/_bazel_kkiningh/5637207f0926cb16b71331d58e1224c0/sandbox
ERROR: /Users/kkiningh/Workspace/Research/bazel_cpp_simple/BUILD:1:1: Linking of rule '//:lib' failed (Exit 1) wrapped_ar failed: error executing command external/local_config_cc/wrapped_ar rcS bazel-out/darwin-fastbuild/bin/liblib.a bazel-out/darwin-fastbuild/bin/_objs/lib/lib.o

Use --sandbox_debug to see verbose messages from the sandbox
src/main/tools/process-wrapper-legacy.cc:58: "execvp(external/local_config_cc/wrapped_ar, ...)": No such file or directory
Target //:lib failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 4.872s, Critical Path: 0.44s
INFO: 1 process: 1 darwin-sandbox.
FAILED: Build did NOT complete successfully
```

Results of `bazel build :lib --noincompatible_use_specific_tool_files`

```
INFO: Build option --incompatible_use_specific_tool_files has changed, discarding analysis cache.
INFO: Analyzed target //:lib (0 packages loaded, 123 targets configured).
INFO: Found 1 target...
Target //:lib up-to-date:
  bazel-bin/liblib.a
  bazel-bin/liblib.so
INFO: Elapsed time: 0.758s, Critical Path: 0.42s
INFO: 3 processes: 3 darwin-sandbox.
INFO: Build completed successfully, 4 total actions
```
