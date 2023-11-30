# This command tells Bazel to load the http_archive rule which is used
# to download other rulesets.
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# ==============================================================================
# gRPC rules
# See https://github.com/grpc/grpc/blob/master/src/cpp/README.md#make
# http_archive(
    # name = "com_github_grpc_grpc",
    # sha256 = "ea281bb3489520ad4fb96ae84b45ed194a1f0b944d3e74f925f5e019d31ecd0f",
    # strip_prefix = "grpc-1.59.3",
    # urls = [
        # "https://github.com/grpc/grpc/archive/refs/tags/v1.59.3.tar.gz",
    # ],
# )

# ==============================================================================
# Protobuf and gRPC rules
# https://rules-proto-grpc.com/
http_archive(
    name = "rules_proto_grpc",
    sha256 = "9ba7299c5eb6ec45b6b9a0ceb9916d0ab96789ac8218269322f0124c0c0d24e2",
    strip_prefix = "rules_proto_grpc-4.5.0",
    urls = ["https://github.com/rules-proto-grpc/rules_proto_grpc/releases/download/4.5.0/rules_proto_grpc-4.5.0.tar.gz"],
)

# ==============================================================================
load("@rules_proto_grpc//:repositories.bzl", "rules_proto_grpc_toolchains", "rules_proto_grpc_repos")
rules_proto_grpc_toolchains()
rules_proto_grpc_repos()

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")
rules_proto_dependencies()
rules_proto_toolchains()

load("@rules_proto_grpc//cpp:repositories.bzl", rules_proto_grpc_cpp_repos  = "cpp_repos")
rules_proto_grpc_cpp_repos()

# ==============================================================================
load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")
grpc_deps()
load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")
grpc_extra_deps()
