# Hello World

This example demonstrates how to play around with our privacy modification to gRPC.

For convenience, the generated `.pb.go` files are already included for you. If you want the full experience, follow these prerequisites to produce them from `helloworld/helloworld/demo.proto` --- otherwise, if you just want to get started, you can skip these steps: 

 1. Install [`protoc`](https://developers.google.com/protocol-buffers/docs/downloads).
 2. Download our modified [`grpc-go`](https://github.com/CSCI-2390-Project/grpc-go). Navigate to `cmd/protoc-gen-go-gprc`, and run `go install .`
 3. Download our modified [`protobuf-go`](https://github.com/CSCI-2390-Project/grpc-go). Navigate to `cmd/protoc-gen-go`, and run `go install .`
 4. `cd helloworld/helloworld/demo.proto` and run using the following command: 

    ```
    protoc --go_out=. --go-grpc_out=. demo.proto
    ```
    
    This will create a folder containing generated `helloworld.pb.go` and `helloworld_grpc.pb.go` for you. Replace the corresponding files in `helloworld/helloworld` with these values. 

Follow these setup to run the [quick start][] example:

 1. Run the server:

    ```console
    cd helloworld/greeter_server/
    GRPC_PRIVACY_POLICY_LOCATION=privacy_policy.json go run .
    ```

 3. Run the client:

    ```console
    cd helloworld/greeter_client/
    go run .
    ```

You can amend the provided `helloworld/greeter_server/privacy_policy.json` file to your heart's content.

For full insight into what's happening under the hood, we recommend enabling debug-level logging by uncommenting line 58 in `greeter_server/main.go`.
