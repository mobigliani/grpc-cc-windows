# grpc-cc-windows
Example of simple gRPC client built with Bazel on Windows.

Build with Bazel:
```
bazel build //helloworld:greeter_client --verbose_failures
```
Build fails with:
```
helloworld/greeter_client.cc(31): fatal error C1083: Cannot open include file: 'helloworld.grpc.pb.h': No such file or directory
```
