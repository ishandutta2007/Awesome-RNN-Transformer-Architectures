# Awesome-RNN-Transformer-Architectures

## Top RPC Frameworks Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on High-Performance Binary Encoding, Streaming & Cross-Language Service Contracts*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **RPC Frameworks**. These tools enable applications to call functions on remote servers as if they were local — handling serialization, transport, code generation, and streaming so distributed systems communicate reliably and efficiently.

**Examples** include gRPC, Apache Thrift, Connect-RPC, tRPC, Twirp, REST, GraphQL, WebSockets, SOAP, and XML-RPC (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, binary encoding, and transparent service contracts — ideal for platform engineers prioritizing performance, avoiding vendor lock-in, and building polyglot microservices that scale.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Cloudflare gRPC** — Managed gRPC routing and load balancing through Cloudflare's edge network, with support for gRPC and gRPC-Web termination without running your own proxy infrastructure.

- **Google Cloud Endpoints** — Managed API management for gRPC and REST services on GCP with authentication, monitoring, and quota management.

- **AWS App Mesh** — Managed Envoy-based service mesh that handles gRPC traffic routing and observability. **End of support: September 30, 2026** — AWS recommends migrating to Amazon ECS Service Connect.

- **Postman** — API platform with gRPC support for testing and debugging gRPC services alongside REST and GraphQL.

## Open-Source GitHub Projects

- **[gRPC](https://github.com/grpc/grpc)**  
  **The de facto standard for high-performance RPC** — Apache 2.0 licensed, **45,000+ GitHub stars**. **Built on HTTP/2 with Protocol Buffers** as the default IDL, delivering binary encoding that is **50%+ smaller than JSON** for equivalent payloads. **Shared C core library** with language-specific implementations for C++, Python, Ruby, Objective-C, PHP, C#, Java, Go, Node.js, and Dart. **Four call patterns**: unary, server streaming, client streaming, and **bidirectional streaming** — the last being a key differentiator over JSON-RPC and REST. **Synchronous and asynchronous APIs** across most languages. **Best for polyglot microservices** (Go calling Python calling Java) and high-frequency service-to-service communication where binary encoding savings are measurable.

- **[Apache Thrift](https://github.com/apache/thrift)**  
  **Facebook's cross-language RPC framework** — Apache 2.0 licensed, one of the oldest and most mature options. **Language-independent with clean abstractions for transport and serialization**. Used by **Dataproc Metastore** as a legacy endpoint protocol alongside gRPC — Thrift is the default preselect, though gRPC is the modern recommended option. **Facebook's fbthrift** is the evolved branch with a new C++ compiler and fully asynchronous server for high-performance RPC. **Best for existing Thrift deployments** and teams needing the widest language support from an established framework.

- **[Connect-RPC](https://github.com/connectrpc/connect-go)**  
  **The modern gRPC-compatible framework from Buf** — Apache 2.0 licensed. **Implements three protocols simultaneously**: gRPC (existing clients), gRPC-Web (browsers), and **Connect protocol** (standard HTTP with curl and browser fetch). **A Connect server is simultaneously a gRPC server, gRPC-Web server, and Connect HTTP server** — write the service once, all three protocols work. **No Envoy proxy required** for browser clients — Connect requests look like normal HTTP/2 requests to browsers and CDNs. **Supports JSON or Protobuf** content types, with **GET requests for queries** enabling HTTP caching. **Best for teams wanting gRPC's type safety and Protobuf encoding with browser compatibility** without gRPC-Web's proxy overhead.

- **[Twirp](https://github.com/twitchtv/twirp)**  
  **Twitch's simple RPC framework with Protobuf service definitions** — Apache 2.0 licensed, **8,000+ GitHub stars**. **Simpler than gRPC** — no HTTP/2 requirement, works over standard HTTP/1.1 and HTTP/2. **Protobuf service definitions** with generated Go clients and servers. **The framework's design philosophy**: "Twirp is a simple RPC framework built on Protobuf. You define a service in a .proto file, and Twirp generates routing and serialization for you, so you can focus on your service's logic". **TwirPHP** provides a PHP port with a protoc plugin and MIT/Apache 2.0 dual licensing. **Best for Go services wanting simplicity over gRPC's full feature set**.

- **[tRPC](https://github.com/trpc/trpc)**  
  **The TypeScript-native RPC framework with zero code generation** — MIT licensed. **No .proto files, no build tooling beyond TypeScript itself** — define your API as TypeScript functions and tRPC infers client types automatically. **When you change a server function's signature, the TypeScript compiler immediately flags every incorrect client call**. **Native React Query integration** for caching and state management. **Limitation**: Only works within TypeScript ecosystems — native mobile apps or non-TypeScript backends need gRPC or REST. **Best for Next.js and TypeScript monorepos** where end-to-end type safety from database to UI is the priority.

- **[Apache bRPC](https://github.com/apache/brpc)**  
  **Baidu's industrial-grade RPC framework in C++** — Apache 2.0 licensed, **17,600+ GitHub stars**. **"Better RPC"** — used internally at Baidu for search, storage, machine learning, advertising, and recommendation at massive scale. **Asynchronous networking foundation** for concurrent connections with pluggable transport interceptors. **Best for high-performance C++ systems** requiring proven industrial-scale RPC.

- **[Google tarpc](https://github.com/google/tarpc)**  
  **Rust RPC framework with async/await support** — MIT licensed, **3,700+ GitHub stars**. **Defines services in code** — no separate schema compilation or language switching. **Generates server traits and client stubs** for network communication. **Asynchronous service interface** allowing remote functions to be called as local async tasks. **Request lifecycle interceptor** for authorization, throttling, and load balancing. **Best for Rust projects** wanting type-safe RPC without Protobuf tooling.

- **[Kitex](https://github.com/cloudwego/kitex)**  
  **ByteDance's high-performance Go RPC framework** — Apache 2.0 licensed, **8,000+ GitHub stars**. **gRPC and Protobuf compatible** with built-in microservices governance. **Proxyless service mesh integration** — manages network traffic directly without sidecar proxy latency. **High-performance communication library** minimizing memory copies. **Best for Go microservices** wanting gRPC compatibility with service governance built in.

### Additional Strong Open-Source Options

- **grpc-go** — Official Go implementation of gRPC. 23,000+ GitHub stars.
- **tonic** — Native gRPC client and server for Rust with async/await, built on hyper and tokio. 12,400+ GitHub stars.
- **MagicOnion** — Modern RPC framework for .NET and Unity with unified real-time communication using gRPC. 4,400+ GitHub stars.
- **RPCX** — High-performance, feature-rich Go microservices framework. 8,300+ GitHub stars.
- **Dubbo** — Java-based RPC and microservices framework for enterprise distributed systems. 41,500+ GitHub stars.
- **Go-zero** — Cloud-native Go microservices framework with built-in RPC and service discovery. 33,300+ GitHub stars.

**Frameworks for building custom systems**: Combine **gRPC** for high-performance cross-language service-to-service communication with native bidirectional streaming, **Connect-RPC** for gRPC type safety with browser compatibility and no proxy, **tRPC** for TypeScript monorepos with end-to-end type inference, **Twirp** for simple Go services without HTTP/2 complexity, and **Apache Thrift** for widest language coverage from an established framework — to build an RPC layer tailored to your language mix, performance requirements, and browser support needs.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- RPC frameworks differ significantly in transport requirements, browser support, and language ecosystems. **gRPC's binary encoding advantage is significant for high-frequency calls** — Protobuf payloads are 50%+ smaller than equivalent JSON at 10M requests/day. **gRPC has poor native browser support** — browsers don't expose the HTTP/2 framing layer needed for gRPC's trailer-based status reporting, requiring gRPC-Web with an Envoy proxy. **Connect-RPC eliminates the proxy requirement** while remaining gRPC-compatible. **tRPC only works within TypeScript ecosystems** — native mobile or non-TypeScript backends need gRPC or REST. **Twirp is simpler than gRPC** — no HTTP/2 requirement, making it suitable for environments where HTTP/2 isn't available. **gRPC streaming is a key differentiator** — bidirectional streaming enables chat, live collaboration, and real-time event delivery that JSON-RPC and SOAP cannot match.
- Self-hosted open-source solutions require proper HTTP/2 infrastructure for gRPC, Protobuf tooling installation, and load balancer configuration that supports gRPC's trailer-based status reporting.

---

**Made for backend engineers, platform teams, and developers building distributed service communication.**
Let's make RPC frameworks more open, performant, and language-agnostic.
