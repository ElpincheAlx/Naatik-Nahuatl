# Na'atik Nahuatl Language Repository

Curated Na’atik packages and approved resources for Nahuatl language support.

Status: published official umbrella catalog; zero published packages.
Canonical static catalog base:
https://raw.githubusercontent.com/ElpincheAlx/Naatik-Nahuatl/main/

PR-0139 Stage 4B externally validated this repository's identity, empty index
and normal empty-catalog behavior. In Na'atik use **Configuración guiada →
Náhuatl → Agregar repositorio**. No package install action is offered. This is
static catalog hosting, not a GitHub Release or production language provider.
These local documentation changes do not publish anything.

## Language profiles — not implemented

This is an umbrella repository for Nahuatl-language resources. Nahuatl must not
be treated as one necessarily homogeneous language implementation. No variety
is selected by this skeleton.

Future profiles must identify the relevant Nahuatl variety using appropriate,
verified language identifiers and document the resource's actual linguistic and
orthographic coverage. Assign resources to the appropriate variety when
applicable; do not claim compatibility across varieties without evidence.

Dictionaries, OCR models, analyzers, grammar databases, speech models and other
language resources are future work. No such implementation, dataset or model is
created or bundled here. Resource provenance and any community/upstream terms
must be reviewed before publication.

## Repository format

This is an empty Na'atik schema-1 repository, following the existing
`internal/repositoryindex` and `internal/repository` implementation and fixtures.
It is not a new manifest format. No packages are currently published or installed.

```text
LICENSE
README.md
RESOURCE_PROVENANCE.md
THIRD_PARTY_NOTICES.md
repository.toml
packages/
  index.txt
```

`repository.toml` requires `schema = 1`, `[repository].id` and
`[repository].display_name`. It also supports repository `description` and
optional `[metadata].maintainer` / `homepage`. The confirmed static base above is maintained centrally in Na'atik, not added
as an unsupported metadata field.

`packages/index.txt` is intentionally zero bytes. The HTTP reader accepts blank
lines/comments and one repository-root-relative release metadata path per entry.
The local published reader recursively discovers `.toml` files under `packages/`;
it does not use index.txt. Both readers therefore return zero releases here.

When a real release is approved, the existing layout uses
`packages/<package-id>/<version>.toml` plus its real `.npkg` artifact under
`packages/<package-id>/`. Release metadata supports `schema`, `[id]` name/version,
`[package]` type, `[compatibility]` core, `[source]` package/sha256/size and
`[metadata]` display_name/description. Source `package` names the artifact; there
is no arbitrary artifact-URL field. The remote reader derives the URL from
`packages/<id.name>/<source.package>`. SHA-256 must be 64 hexadecimal characters;
size must be positive. An artifact's internal `naatik.toml` is a separate package
manifest. Do not invent a release entry, size, checksum or artifact in this skeleton.

The official catalog is published. PR-0139 Stage 1 fixed Na'atik's repository URL
resolution to preserve configured path prefixes and reject relative paths that
escape the base. PR-0139 Stage 4B validated the static base by retrieving repository.toml and
the zero-byte packages/index.txt. Recheck connectivity when qualifying a new
distribution; historical public validation is not a fresh network check. A GitHub
source repository URL is not itself a confirmed static catalog base. No new metadata fields are needed; use the confirmed raw base above.

## License and provenance

Original metadata/documentation/code: **PolyForm Noncommercial License 1.0.0**,
SPDX `PolyForm-Noncommercial-1.0.0`; source-available for noncommercial use.
Required Notice: Copyright (c) 2026 Alx Hndz

See [LICENSE](LICENSE), [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and
[RESOURCE_PROVENANCE.md](RESOURCE_PROVENANCE.md). Third-party resources retain
their own terms; no legal or redistribution approval is implied.
