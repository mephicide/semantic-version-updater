# (Semantic) Version Updater

A simple tool for updating versions of both dependencies and main artifact versions in CI pipelines based on semantic versioning. The main use-cases are:

- Explicitly set a dependency version to the new one produced by a successful pipeline run
- Bump the semantic version of the artifact produced by a repo's build pipeline. This could happen at the same time as the previous use-case

Typically, a chain of CI pipelines need to trigger updates to dependent projects once an acceptable testing outcome has been achieved, and you still want team membebrs to be able to clone a repo that has been auto-managed in this way and have a complete, working dependency file without any variables. This tool is aimed at solving that issue.

# Installation

TBD

# Examples

## Set some dependency versions to new ones from a prior CI pipeline, and bump the major version (package.json)

`update-version --set-dependencies react=1.2.3,react-dom=2.3.4 package1.json --bump major`

## Update the patch version in the .gitlab-ci.yml

`update-version --bump patch .gitlab-ci.yml`

## Update a dependency and main version of setup.py

`update-version --set-dependencies semver=4.5.6 setup.py --bump major`

## Update a dependency in requirements.txt; ignore bumping the main version which is meaningless

`update-version --set-dependencies gtfs-realtime-bindings=4.5.6 foo-requirements.txt --bump major`
