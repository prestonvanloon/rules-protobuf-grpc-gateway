# Rules Protobuf Grpc Gateway Bug Example



To replicate error:

```
bazel build :gateway
```

Produces:
```
➜  rules-protobuf-grpc-gateway git:(master) ✗ bazel build :gateway
WARNING: /home/preston/.cache/bazel/_bazel_preston/729315b556e626a4cf0a757c09c988f1/external/org_pubref_rules_protobuf/protobuf/internal/proto_compile.bzl:390:5: 
************************************************************
cd $(bazel info execution_root) && bazel-out/host/bin/external/com_github_google_protobuf/protoc \ 
--descriptor_set_out=bazel-out/local-fastbuild/genfiles/gateway.pb.descriptor_set \ 
--plugin=protoc-gen-go=bazel-out/host/bin/external/com_github_golang_protobuf/protoc-gen-go/protoc-gen-go \ 
--go_out=Mgoogle/api/annotations.proto=github.com/grpc-ecosystem/grpc-gateway/third_party/googleapis/google/api,Mtest-grpc-gateway.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway,Mtest-resource.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway,Mtest-webhook-messages.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway,plugins=grpc:bazel-out/local-fastbuild/genfiles \ 
--proto_path=external/com_github_google_protobuf/src/ \ 
--proto_path=external/com_github_grpc_ecosystem_grpc_gateway/third_party/googleapis/ \ 
--proto_path=. \ 
test-grpc-gateway.proto \ 
test-resource.proto \ 
test-webhook-messages.proto
************************************************************
test-grpc-gateway.pb.go
test-resource.pb.go
test-webhook-messages.pb.go
gateway.pb.descriptor_set
************************************************************
.
WARNING: /home/preston/.cache/bazel/_bazel_preston/729315b556e626a4cf0a757c09c988f1/external/org_pubref_rules_protobuf/protobuf/internal/proto_compile.bzl:390:5: 
************************************************************
cd $(bazel info execution_root) && bazel-out/host/bin/external/com_github_google_protobuf/protoc \ 
--descriptor_set_out=bazel-out/local-fastbuild/genfiles/gateway.gw.descriptor_set \ 
--plugin=protoc-gen-grpc-gateway=bazel-out/host/bin/external/com_github_grpc_ecosystem_grpc_gateway/protoc-gen-grpc-gateway/protoc-gen-grpc-gateway \ 
--grpc-gateway_out=Mgoogle/api/annotations.proto=github.com/grpc-ecosystem/grpc-gateway/third_party/googleapis/google/api,Mtest-grpc-gateway.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway,Mtest-resource.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway,Mtest-webhook-messages.proto=github.com/prestonvanloon/rules-protobuf-grpc-gateway/gateway:bazel-out/local-fastbuild/genfiles \ 
--proto_path=external/com_github_google_protobuf/src/ \ 
--proto_path=external/com_github_grpc_ecosystem_grpc_gateway/third_party/googleapis/ \ 
--proto_path=. \ 
test-grpc-gateway.proto \ 
test-resource.proto \ 
test-webhook-messages.proto
************************************************************
test-grpc-gateway.pb.gw.go
test-resource.pb.gw.go
test-webhook-messages.pb.gw.go
gateway.gw.descriptor_set
************************************************************
.
INFO: Found 1 target...
ERROR: /home/preston/rules-protobuf-grpc-gateway/BUILD:7:1: output 'test-resource.pb.gw.go' was not created.
ERROR: /home/preston/rules-protobuf-grpc-gateway/BUILD:7:1: output 'test-webhook-messages.pb.gw.go' was not created.
ERROR: /home/preston/rules-protobuf-grpc-gateway/BUILD:7:1: not all outputs were created or valid.
Target //:gateway failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 9.680s, Critical Path: 4.42s
```