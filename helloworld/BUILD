cc_binary(
    name = "greeter_client",
    srcs = ["greeter_client.cc"],
    deps = [
        "//helloworld/protos:helloworld_cc_grpc",
        "@com_github_grpc_grpc//:grpc++",
        "@com_google_absl//absl/flags:parse",
    ],
)
