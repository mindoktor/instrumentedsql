# Docly customized fork

Due to various problems discovered when moving our main repository to go modules, we require the use of an older, and customized, version of the `instrumentedsql` package,. This is based on v1.0.1. Reason for the fork: The `google` sub package contained an unversioned reference to the package `cloud.google.com/go/trace`. This no longer exists, and could not be resolved when moving our repo to go modules. The solution was to unreference the sub package by deleting the test file, and also deleting the `google` folder.

Our customizations:

- Removed test file.
- Removed `google` sub package, only referenced from the test file.
- Changed internal package names.
- Ran go mod tidy.
- Added documentation to this README file.

[![GoDoc](https://godoc.org/github.com/luna-duclos/instrumentedsql?status.svg)](https://godoc.org/github.com/luna-duclos/instrumentedsql)

# instrumentedsql

A sql driver that will wrap any other driver and log/trace all its calls

## How to use

Please see the [documentation](https://godoc.org/github.com/luna-duclos/instrumentedsql) and [examples](https://github.com/luna-duclos/instrumentedsql/blob/master/sql_example_test.go)

## Roadmap

Reach API stability and decide what is in/out of scope for this package.
current plan is to include tracing, logging, metrics, and anything else that might fit into a wrapper, keeping everything optional and disabled by default.

## Contributing

PRs and issues are welcomed and will be responded to in a timely fashion, please contribute!

Contributors will contain all people (not companies) that have contributed to the project.
LICENSE will list all copyright holders.
