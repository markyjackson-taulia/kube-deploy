load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "proto2.pb.go",
        "proto2_ext.pb.go",
        "proto2_ext2.pb.go",
        "test.pb.go",
    ],
    importpath = "google.golang.org/grpc/reflection/grpc_testing",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
    ],
)

proto_library(
    name = "grpc_testing_proto",
    srcs = [
        "proto2.proto",
        "proto2_ext.proto",
        "proto2_ext2.proto",
        "test.proto",
    ],
    visibility = ["//visibility:public"],
    deps = ["//:apiserver-builder_proto"],
)

go_grpc_library(
    name = "grpc_testing_go_proto",
    importpath = "google.golang.org/grpc/reflection/grpc_testing",
    proto = ":grpc_testing_proto",
    visibility = ["//visibility:public"],
    deps = ["//:go_default_library"],
)
