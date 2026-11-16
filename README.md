# Landtrek Connect Lite

A performance-focused derivative of Open Headunit 4.0.0, intended to remain a real
Android Auto receiver rather than a web simulation.

**This repository currently contains documentation and attribution only.** The
implementation is being prepared for publication. No Landtrek APK is published here,
and this repository is not yet a buildable source release.

## Upstream foundation

The Android Auto receiver, USB/wireless connection paths, protocol/TLS transport,
video decoding, audio, touch pipelines, settings and existing tests come from
[Open Headunit](https://github.com/andreknieriem/open-headunit), based on
[Michael Reid's original headunit project](https://github.com/mikereidis/headunit).
The reference release is Open Headunit **v.4.0.0**, commit
`5511654d0d01ec72db34f94befbcebcab3f8af23`.

We preserve upstream attribution and AGPL-3.0-or-later obligations. See the included
`LICENSE` and `COPYRIGHT_MICHAEL_REID_GPLv3AFFERO.txt`. We do not claim authorship of
Android Auto, Maps, music applications or the upstream receiver/media stack.

## Changes developed for Landtrek

- Separate `com.landtrek.connectlite` application identity, fork-scoped integration
  identifiers and prevention of upstream application update offers.
- Manual, Auto, Ultra Lite, Balanced and Performance profiles, with conservative
  capability fallbacks and a negotiation target fixed for each active session.
- Fewer temporary allocations in the existing performance-overlay helper, while
  preserving its output.
- Explicit-device diagnostic tooling, correct partial-memory reporting, additional
  regression tests and a repeatable host allocation benchmark.
- Compatibility, performance-evidence and dependency/native-provenance documentation.

## Verification and limitations

The local debug alpha passed 4,838 JVM tests and 16 Python/artifact tests. Its package
identity and debug signature were checked. Host helper benchmarks observed about
35% fewer allocations within that workload, **not** a 35% reduction in Android-wide
RAM use or an improvement in device FPS.

Physical Feonal/A54 compatibility, sustained projection, audio, touch and performance
acceptance remain unverified. Profiles are negotiated targets, not guarantees.

## APK and source publication status

APK distribution is paused pending verification of native-library corresponding
source/provenance, FFmpeg source delivery, Google Nearby redistribution/AGPL
compatibility and complete dependency notices. These are unresolved evidence and
compliance questions, not a claim that distribution has been proven unlawful.

The existing development history also requires a publication-safety audit before
upload. It has deliberately not been pushed into this documentation-only repository.
There is no download link or release yet. Any future APK release must include its
source-access information, notices, checksum and explicit alpha/device-test limitations.
