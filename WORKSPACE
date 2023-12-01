# This command tells Bazel to load the http_archive rule which is used
# to download other rulesets.
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# ==============================================================================
# gRPC Rules for Bazel.
# See https://github.com/grpc/grpc/blob/master/src/cpp/README.md#make
http_archive(
    name = "com_github_grpc_grpc",
    sha256 = "437068b8b777d3b339da94d3498f1dc20642ac9bfa76db43abdd522186b1542b",
    strip_prefix = "grpc-1.60.0",
    urls = [
        "https://github.com/grpc/grpc/archive/refs/tags/v1.60.0.tar.gz",
    ],
)
load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")
grpc_deps()
load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")
grpc_extra_deps()
