# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog][1], and this project adheres to [Semantic Versioning][2].

[1]: https://keepachangelog.com/en/1.0.0/
[2]: https://semver.org/spec/v2.0.0.html

## [1.0.0] — 18 November 2019

### Changed

- Revised Manifests handling.
  - Revised Manifests so they are validated once, during creation.
    - Empty Manifests are now invalid.
    - Manifests can be valid or invalid depending on their entries.
    - See documentation for `Packmatic.Manifest`.
  - Revised Encoder to not re-validate Manifests.
    - Encoder halts immediately if given an invalid Manifest.
  - Removed `Packmatic.Validator.validate_each/1`.
    - Since the Manifest is validated as it is built, this function is no longer useful.
  - Revised tests.
    - Revised test on “no entries” case for invalid Manifest.
    - Added simple Manifest test with examples.
    - Made the top-level PackmaticTest asynchronous.

- Revised Sources handling.
  - Eliminated duplicative types with code generation.
    - Known Sources are referred by name.
    - The Source Entry type is generated based on the names.
  - Revised individual Source modules.
    - Standardised nomenclature (`init_arg`, `init_result`, etc) for type handling.
  - Revised Manifest types.
    - Removed aliasing of `Manifest.Entry.t()`.
    - Renamed `Manifest.entry_keyword()` to `Manifest.Entry.proplist()`.
  - Added further documentation on how Dynamic Sources work.
    - Added documentation within `Packmatic.Source.Dynamic`.
    - Added ExDoc test for inlined snippets.

## [0.1.0] — 30 October 2019

### Added

- Initial Release.

[unreleased]: https://github.com/evadne/packmatic/compare/master...develop
[1.0.0]: https://github.com/evadne/packmatic/releases/tag/v1.0.0
[0.1.0]: https://github.com/evadne/packmatic/releases/tag/v0.1.0
