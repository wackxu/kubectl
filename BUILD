load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "explain.go",
        "field_lookup.go",
        "fields_printer.go",
        "fields_printer_builder.go",
        "formatter.go",
        "model_printer.go",
        "recursive_fields_printer.go",
        "typename.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubectl/explain",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/k8s.io/apimachinery/pkg/api/meta:go_default_library",
        "//vendor/k8s.io/kube-openapi/pkg/util/proto:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "explain_test.go",
        "field_lookup_test.go",
        "fields_printer_test.go",
        "formatter_test.go",
        "model_printer_test.go",
        "recursive_fields_printer_test.go",
        "typename_test.go",
    ],
    data = ["test-swagger.json"],
    importpath = "k8s.io/kubernetes/pkg/kubectl/explain",
    library = ":go_default_library",
    deps = [
        "//pkg/kubectl/cmd/testing:go_default_library",
        "//pkg/kubectl/cmd/util/openapi/testing:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/meta:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
    ],
)
