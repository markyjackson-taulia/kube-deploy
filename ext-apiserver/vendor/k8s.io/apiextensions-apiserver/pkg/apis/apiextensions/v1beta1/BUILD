load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "conversion.go",
        "deepcopy.go",
        "defaults.go",
        "doc.go",
        "generated.pb.go",
        "marshal.go",
        "register.go",
        "types.go",
        "types_jsonschema.go",
        "zz_generated.conversion.go",
        "zz_generated.deepcopy.go",
        "zz_generated.defaults.go",
    ],
    importpath = "k8s.io/apiextensions-apiserver/pkg/apis/apiextensions/v1beta1",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/sortkeys:go_default_library",
        "//vendor/k8s.io/apiextensions-apiserver/pkg/apis/apiextensions:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/conversion:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/json:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "conversion_test.go",
        "marshal_test.go",
    ],
    importpath = "k8s.io/apiextensions-apiserver/pkg/apis/apiextensions/v1beta1",
    library = ":go_default_library",
    deps = [
        "//vendor/k8s.io/apiextensions-apiserver/pkg/apis/apiextensions:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
    ],
)

proto_library(
    name = "v1beta1_proto",
    srcs = ["generated.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//k8s.io/apimachinery/pkg/apis/meta/v1:v1_proto",
        "//k8s.io/apimachinery/pkg/runtime:runtime_proto",
        "//k8s.io/apimachinery/pkg/runtime/schema:schema_proto",
        "//k8s.io/apimachinery/pkg/util/intstr:intstr_proto",
    ],
)

go_proto_library(
    name = "v1beta1_go_proto",
    importpath = "k8s.io/apiextensions-apiserver/pkg/apis/apiextensions/v1beta1",
    proto = ":v1beta1_proto",
    visibility = ["//visibility:public"],
    deps = [
        "//k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//k8s.io/apimachinery/pkg/util/intstr:go_default_library",
    ],
)
