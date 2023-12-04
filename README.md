# grpc-cc-windows
Example of simple gRPC client built with Bazel on Windows.

Build with Bazel:
```
bazel build //helloworld:greeter_client --verbose_failures
```

When building on Windows, compiler may complain about missing protobuf or other external headers. This usually indicates  paths too long for MSVC compiler. To mitigate the issue one can set custom output directory to shorten the paths.
It can be done either by adding `startup --output_user_root=C:/ur` to `c:\ProgramData\bazel.bazelrc` file, or `startup --output_base=C:/o` to `.bazelrc` in current workspace.

Example PS command:
```
echo 'startup --output_user_root=C:/o' | out-file -encoding ASCII C:\ProgramData\bazel.bazelrc
```

[Long path support](https://learn.microsoft.com/en-us/windows/win32/fileio/maximum-file-path-limitation?tabs=registry) required in Windows, to enable it type in PS console (requires restart):
```
Set-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\FileSystem' -Name 'LongPathsEnabled' -Value 1
```
