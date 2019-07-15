# VRI Example using OpenAPI

> This example uses the JSON Schema version of the NIST 1500-102 Voter Records Interchange Common Data FOrmat

This prototype shows how an election agency could host a voter registration endpoint
using the [Voter Records Interchange Common Data Format](https://github.com/usnistgov/VoterRecordsInterchange). [OpenAPI](https://www.openapis.org/) is used to describe
the `HTTP` semantics of the interface.

In the [OpenAPI document](./swagger.yaml), we describe a single endpoint `/voterReg` where
voter registration data can submitted to the server via `HTTP` `POST`. We specify
the content of the exchange as using the `VoterRecordsRequest` object. The response can be any of the three standard responses, i.e. `RecordsAcknowledgement`, `RecordsRejection` or `RecordsSuccess`.

There are numerous advantages to documenting your APIs using OpenAPI:

- Automatically generate documentation and metadata webpages
- Automatic generation of [client and server boilerplate](https://github.com/OpenAPITools/openapi-generator). The server boilerplate can be used the jurisdiction, while the client boilerplate could be used by a third party registrar.
- [Tooling support]() for editing OpenAPI documents

## Try it out

Visit the [generated documentation](https://jdziurlaj.github.io/VRIExamples/index.html).