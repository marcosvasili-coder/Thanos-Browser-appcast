# Thanos Browser appcast

Sparkle update metadata for [Thanos Browser](https://github.com/marcosvasili-coder/Thanos-Browser).
Application source and release tooling live in that separate repository.

## Contents

[appcast.xml](appcast.xml) is an RSS/Sparkle feed containing release items,
version/build identifiers, minimum macOS versions and download enclosures.
The checked-in enclosures point to this repository's GitHub Releases and carry
Sparkle EdDSA signatures. The feed itself is not an application build.

The comment in `appcast.xml` documents the ordering and version contract:
newest items first; `sparkle:version` corresponds to the shipped
`CFBundleVersion`, and `sparkle:shortVersionString` to the marketing version.
It names `scripts/sparkle/publish_release.sh` and the Release macOS workflow
in the application repository as the publishing entry points.

Do not edit historical signed release items or replace release payloads as
routine documentation maintenance. Publishing, signing and release changes are
separate operations requiring their own authority. Never commit signing keys,
credentials or tokens here.
