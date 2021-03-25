# Spotify Web API Tools

[![Build](https://github.com/sonallux/spotify-web-api/workflows/Build/badge.svg)](https://github.com/sonallux/spotify-web-api/actions?query=workflow%3ABuild)
[![Update API documentation](https://github.com/sonallux/spotify-web-api/workflows/Update%20API%20documentation/badge.svg)](https://github.com/sonallux/spotify-web-api/actions?query=workflow%3A%22Update+API+documentation%22)
[![GitHub](https://img.shields.io/github/license/sonallux/spotify-web-api)](https://github.com/sonallux/spotify-web-api/blob/master/LICENSE)

This monorepo contains tools for parsing the [Spotify Web API Reference](https://developer.spotify.com/documentation/web-api/reference-beta) into a machine-readable format and generating an [Open API Specification](https://github.com/OAI/OpenAPI-Specification) and a java wrapper for Spotify's Web API.

## Modules

| Module | Description |
| --- | --- |
| [spotify-web-api-core](spotify-web-api-core/README.md) | Contains the model for the Spotify Web API Reference | 
| [spotify-web-api-parser](spotify-web-api-parser/README.md) | The parser for the Spotify Web API Reference | 
| [spotify-web-api-generator-open-api](spotify-web-api-generator-open-api/README.md) | Generates an Open API Specification for Spotify's Web API |
| [spotify-web-api-generator-java](spotify-web-api-generator-java/README.md) | Generates a Java wrapper for Spotify's Web API |
| [spotify-web-api-generator-ts](spotify-web-api-generator-ts/README.md) | Generates a TypeScript wrapper for Spotify's Web API |
| [spotify-web-api-java](spotify-web-api-java/README.md) | Contains the java wrapper for Spotify's Web API generated by the [spotify-web-api-generator-java](spotify-web-api-generator-java/README.md) |

## Why the effort of parsing Spotify's web API reference
- Automated API wrapper generation
- Get notified about changes


## Versioning
Unfortunately Spotify does not provide any version information with their web API reference documentation. Therefore, I try to follow [semantic versioning](https://semver.org) when releasing new versions. But keep in mind that Spotify can update their Web API endpoints at any time so that your code can potentially break. Therefore, it is best to always use the very latest version of these libraries. Not updating does always impose the risk of running into issues because Spotify has made a breaking change to their Web API.

## Disclaimer
Because the wrappers are only based on the Spotify web API reference, there might be difference to the actual behaviour of the actual Spotify Web API endpoints. Also, neither do I have any connections to Spotify nor am I an employee at Spotify.

## How to release a new version
1. Update the version number with `./mvnw versions:set -DnewVersion="<version>" -DgenerateBackupPoms=false`
2. Commit and push changes to GitHub
3. Wait till CI is green
4. Tag and push the commit created in step 1. A GitHub actions workflow will automatically deploy the artifacts to Maven Central.
