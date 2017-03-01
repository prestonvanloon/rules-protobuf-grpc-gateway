load("@org_pubref_rules_protobuf//grpc_gateway:rules.bzl", "grpc_gateway_proto_library")

load("@io_bazel_rules_go//go:def.bzl", "go_prefix")
go_prefix("github.com/prestonvanloon/rules-protobuf-grpc-gateway")

grpc_gateway_proto_library(
    name = "gateway",
    imports = [
        "external/com_github_google_protobuf/src/",
        "external/com_github_grpc_ecosystem_grpc_gateway/third_party/googleapis/",
    ],
    inputs = [
        "@com_github_google_protobuf//:well_known_protos",
        "@com_github_grpc_ecosystem_grpc_gateway//third_party/googleapis/google/api:go_default_library_protos",
    ],
    protos = [
        "test-grpc-gateway.proto",
        "test-resource.proto",
        "test-webhook-messages.proto",
    ],
    verbose = 1,
)
