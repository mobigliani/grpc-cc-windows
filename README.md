# grpc-cc-windows
Example of simple gRPC client built with Bazel on Windows.

Build with Bazel:
```
bazel build //helloworld:greeter_client --verbose_failures
```

When building on Windows, compiler may complain about missing protobuf or other external headers. This usually indicates  paths too long for the MSVC compiler. To mitigate the issue one can set custom output directory to shorten the paths.
It can be done either by adding `startup --output_user_root=C:/ur` to `c:\ProgramData\bazel.bazelrc` file, or `startup --output_base=C:/o` to `.bazelrc` in current workspace.
