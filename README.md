# GitHub Action: Upload RPMs the oVirt way 

This simple action takes a directory, creates an RPM repository and uploads the resulting RPM repository as a build artifact in a standardized way.

This is intended for oVirt projects to use as a standard way to archive built RPMs.

## Usage:

```
name: Self-test
on:
  push:
  pull_request:
jobs:
  selftest:
    name: Self-test
    runs-on: ubuntu-latest
    container: quay.io/ovirt/buildcontainer:stream8
    steps:
    - name: Upload artifacts
      uses: .
      with:
        directory: test-artifacts
```