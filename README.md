# VRI Example using OpenAPI

<!-- TOC -->

- [VRI Example using OpenAPI](#vri-example-using-openapi)
    - [Overview](#overview)
    - [Details](#details)
    - [Additional considerations](#additional-considerations)
    - [Try it out](#try-it-out)

<!-- /TOC -->

## Overview

Many jurisdictions are looking at ways to modernize their voter registration systems. A popular approach is to create a set of services or APIs that can be defined once and reused across the solution.

This prototype shows how an election agency could host a voter registration service endpoint
using the [Voter Records Interchange Common Data Format](https://github.com/usnistgov/VoterRecordsInterchange). [OpenAPI (formerly Swagger)](https://www.openapis.org/) is used to describe the web semantics of the service interface.

There are numerous advantages to building services using OpenAPI:

- Automatic generation of documentation [(example)](https://hiltonroscoe.github.io/VRIExamples/index.html) and metadata webpages.
- Automatic generation of [client and server stubs](https://github.com/OpenAPITools/openapi-generator). The server stubs can be used by the jurisdiction, while the client boilerplate could be used by a third party agency, such as a motor vehicle agency or third party registrar.
- [Tooling support](https://swagger.io/tools/open-source/) for editing OpenAPI documents.
- Documentation and implementation are always in sync because they are derived from the same source.

Most of all, OpenAPI makes the most of scarce IT resources by reducing the amount of effort required to create a Web API.

## Details

> This example uses the JSON Schema version of the NIST 1500-102 Voter Records Interchange Common Data Format

In the [OpenAPI contract](./swagger.yaml), we describe a single endpoint located at `/voterReg` where voter registration data can submitted to the server via the `HTTP` transport using the `POST` verb. We specify the content of the exchange as using the `VoterRecordsRequest` object. The response can be any of the three standard responses, i.e. `RecordsAcknowledgement`, `RecordsRejection` or `RecordsSuccess`.

Note how short the contract is, less then fifty lines! This is because OpenAPI has native support for the [JSON Schema provided by NIST](https://github.com/usnistgov/VoterRecordsInterchange/blob/master/NIST_V0_voter_records_interchange.json), freeing us from having to define the details of the data format.

The `swagger.yaml` can be used to generate the web client, web server stubs, and documentation.

## Additional considerations

Security is out of scope of this example. However, it should be noted that OpenAPI supports a number of different [authentication and authorization](https://swagger.io/docs/specification/authentication/) mechanisms.

## Try it out

- Generated Documentation
  - View the [generated documentation](https://hiltonroscoe.github.io/VRIExamples/index.html).
- Editor / Generator
  - Open the [Swagger Editor](https://editor.swagger.io/).
  - Click `File`, `Import URL`.
  - Enter `https://raw.githubusercontent.com/JDziurlaj/VRIExamples/master/swagger.yaml` into the text box, then click `OK`.
  - You can now edit the file, or generate clients.
