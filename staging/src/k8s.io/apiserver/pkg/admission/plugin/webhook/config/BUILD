load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "authentication.go",
        "client.go",
        "kubeconfig.go",
        "serviceresolver.go",
    ],
    importmap = "k8s.io/kubernetes/vendor/k8s.io/apiserver/pkg/admission/plugin/webhook/config",
    importpath = "k8s.io/apiserver/pkg/admission/plugin/webhook/config",
    visibility = ["//visibility:public"],
    deps = [
        "//staging/src/k8s.io/api/admission/v1beta1:go_default_library",
        "//staging/src/k8s.io/api/admissionregistration/v1beta1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime/serializer:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/errors:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/validation/field:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/admission/plugin/webhook/config/apis/webhookadmission:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/admission/plugin/webhook/config/apis/webhookadmission/v1alpha1:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/admission/plugin/webhook/errors:go_default_library",
        "//staging/src/k8s.io/client-go/rest:go_default_library",
        "//staging/src/k8s.io/client-go/tools/clientcmd:go_default_library",
        "//staging/src/k8s.io/client-go/tools/clientcmd/api:go_default_library",
        "//vendor/github.com/hashicorp/golang-lru:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "authentication_test.go",
        "serviceresolver_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/api/equality:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/diff:go_default_library",
        "//staging/src/k8s.io/client-go/rest:go_default_library",
        "//staging/src/k8s.io/client-go/tools/clientcmd/api:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//staging/src/k8s.io/apiserver/pkg/admission/plugin/webhook/config/apis/webhookadmission:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
