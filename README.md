# draco-updates

This repository stores DracolaxOS update metadata and release files.

## Purpose

DracolaxOS uses this repository as an update source for:

- online updates
- offline update packages
- release bundles
- stable and test versions

## Repository layout

```text
index.json
latest.json
stable/
beta/
releases/
```

### `index.json`

The main update index.

It lists components, versions, download links, and update flags.

### `latest.json`

A small stable pointer file.

It tells the system which versions are current.

### `stable/`

Contains tested and safe update packages.

### `beta/`

Contains experimental or test packages.

### `releases/`

Contains release bundles and packaged system update files.

## Update flow

DracolaxOS reads `index.json`, compares it with the local system manifest, downloads the needed package, stages it, validates it, then applies it.

If the update fails, the system can rollback to the previous version.

## File format

Update packages use the `.drxpkg` format.

A package should contain:

- a package manifest
- update files
- checksums
- optional scripts

## Local offline updates

Users can also download a `.drxpkg` file and install it locally.

This is useful when the system has no internet access or when a known good version is needed.

## Release policy

Only push releases that are tested.

Use stable for normal users.

Use beta only for testing.

## License

MIT
