# Valtira TCGdex catalog artifacts

This public repository distributes generated catalog artifacts used by Valtira.
Canonical card and set data originates from the official
[TCGdex cards database](https://github.com/tcgdex/cards-database).

Each artifact directory is generated from a pinned upstream commit. Its
`manifest.json` records source provenance, artifact format version,
normalization version, and SHA-256 checksums. Valtira applies the documented,
versioned compatibility normalization layer during generation.

Artifact format 2 adds `pokemon-search/index.json` and immutable per-species
shards. Card membership comes exclusively from TCGdex's compiled National
Pokédex IDs. The pinned TCGdex revision's own dex-fixer uses PokeAPI as its
species-name authority, so the manifest also records the exact pinned PokeAPI
commit and English-name CSV checksum. PokeAPI supplies lookup labels only;
TCGdex remains canonical for card and set identity.

Do not manually edit generated files. Runtime consumers must pin a complete,
immutable Git commit SHA and verify the manifest digest and artifact checksums.

## Attribution and license

The upstream TCGdex database is Copyright (c) 2021 TCGdex and licensed under
the MIT License. See [LICENSE](LICENSE). This database is not produced,
endorsed, supported, or affiliated with Nintendo or The Pokémon Company.
