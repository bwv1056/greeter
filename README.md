# greeter
unary grpc sample

# generate
protoc -I ./grpc/ \
--go_out=plugins=grpc:. \
--go_opt=module=github.com/bwv1056/greeter \
./grpc/*.proto

# client
grpcurl -plaintext -proto grpc/greeter.proto -d '{"name": "world"}' localhost:50051 greeter.Greeter/SayHello
