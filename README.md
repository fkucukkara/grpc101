# gRPC 101 - Basic Client/Server Communication

This repository contains a basic demonstration of gRPC communication between a client and server using .NET. It serves as a 101 playground project to understand how gRPC works in a .NET environment.

## Project Structure

The solution consists of two projects:

- **GrpcGreeterServer**: A gRPC server implementation
- **GrpcGreeterClient**: A console application that acts as a gRPC client

## Prerequisites

- .NET 9.0 SDK or later
- Visual Studio 2022 or VS Code

## Key Features

- Basic gRPC service definition using Protocol Buffers
- Simple request-response pattern demonstration
- Async communication between client and server

## Quick Start

1. Clone the repository:
```bash
git clone https://github.com/[your-username]/GrpcGreeter.git
cd GrpcGreeter
```

2. Start the server:
```bash
cd GrpcGreeterServer
dotnet run
```

3. In a new terminal, run the client:
```bash
cd GrpcGreeterClient
dotnet run
```

## Technical Details

### Protocol Definition

The service is defined in `Protos/greet.proto`:

```protobuf
service Greeter {
  rpc SayHello (HelloRequest) returns (HelloReply);
}

message HelloRequest {
  string name = 1;
}

message HelloReply {
  string message = 1;
}
```

### Server Implementation

- Uses ASP.NET Core
- Implements the gRPC service defined in the proto file
- Listens on port 5106 by default

### Client Implementation

- Console application using `Grpc.Net.Client`
- Demonstrates basic connection and request to the gRPC server
- Shows simple message exchange

## Dependencies

Server:
- Grpc.AspNetCore (2.64.0)

Client:
- Google.Protobuf (3.30.2)
- Grpc.Net.Client (2.71.0)
- Grpc.Tools (2.72.0)

## Learning Resources

- [Introduction to gRPC on .NET](https://learn.microsoft.com/en-us/aspnet/core/grpc/)
- [gRPC for .NET Examples](https://github.com/grpc/grpc-dotnet/tree/master/examples)
- [Protocol Buffers Documentation](https://protobuf.dev/)

## License
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This project is licensed under the MIT License, which allows you to freely use, modify, and distribute the code. See the [`LICENSE`](LICENSE) file for full details.
