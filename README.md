# RadarCOVID DP^3T Fork

<p align="center">
    <a href="https://github.com/RadarCOVID/radar-covid-backend-dp3t-server/commits/" title="Last Commit"><img src="https://img.shields.io/github/last-commit/RadarCOVID/radar-covid-backend-dp3t-server?style=flat"></a>
    <a href="https://github.com/RadarCOVID/radar-covid-backend-dp3t-server/issues" title="Open Issues"><img src="https://img.shields.io/github/issues/RadarCOVID/radar-covid-backend-dp3t-server?style=flat"></a>
    <a href="https://github.com/RadarCOVID/radar-covid-backend-dp3t-server/blob/master/LICENSE" title="License"><img src="https://img.shields.io/badge/License-MPL%202.0-brightgreen.svg?style=flat"></a>
</p>

Fork from [DP3T-Backend-SDK](https://github.com/DP-3T/dp3t-sdk-backend) with the following changes:

- Functional:
  - When a patient gets a verification code, he/she will set the code in the mobile application to report the exposition keys.
  - Mobile application will connect to the Verification Service to check the code validation. If it is valid, Verification Service will return a token.
  - Mobile application will connect to this service (DP3T Server) with the JWT and exposition keys.
  - DP3T Server will get the information from the token and communicate with Verification Service to redeem the Transaction Number (TAN).

  ![Sequence diagram to notify infection](documentation/sequence-diagram-notify-infection.svg)

  You can find these changes in this [package](./dpppt-backend-sdk/dpppt-backend-sdk-ws/src/main/java/org/dpppt/backend/sdk/ws/radarcovid).

- Technical:
  - OpenAPI generation using [springdoc-openapi](https://github.com/springdoc/springdoc-openapi).
  - Protocol Buffers compilation with [protoc-jar-maven-plugin](https://github.com/os72/protoc-jar-maven-plugin) and moving `.proto` files to [`dpppt-backend-sdk-model/src/main/proto`](./dpppt-backend-sdk/dpppt-backend-sdk-model/src/main/proto).
  - Upgraded versions (PostgreSQL, Tomcat, Spring Boot,...).

## Support and Feedback
The following channels are available for discussions, feedback, and support requests:

| Type       | Channel                                                |
| ---------- | ------------------------------------------------------ |
| **Issues** | <a href="https://github.com/RadarCOVID/radar-covid-backend-dp3t-server/issues" title="Open Issues"><img src="https://img.shields.io/github/issues/RadarCOVID/radar-covid-backend-dp3t-server?style=flat"></a> |

## Contribute

If you want to contribute with this exciting project follow the steps in [How to create a Pull Request in GitHub](https://opensource.com/article/19/7/create-pull-request-github).

More details in [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

This Source Code Form is subject to the terms of the [Mozilla Public License, v. 2.0](https://www.mozilla.org/en-US/MPL/2.0/).
