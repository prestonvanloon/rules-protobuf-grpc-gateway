git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.4.0",
)
load("@io_bazel_rules_go//go:def.bzl", "go_repositories")

go_repositories()

git_repository(
  name = "org_pubref_rules_protobuf",
  remote = "https://github.com/pubref/rules_protobuf",
  tag = "v0.7.1",
  #commit = "..." # alternatively, latest commit on master
)

load("@org_pubref_rules_protobuf//go:rules.bzl", "go_proto_repositories")
go_proto_repositories()

load("@org_pubref_rules_protobuf//grpc_gateway:rules.bzl", "grpc_gateway_proto_repositories")
grpc_gateway_proto_repositories()
