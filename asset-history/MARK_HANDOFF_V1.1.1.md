# Mark Handoff — Audio ZH/JA V1.1.1

## Purpose

This file tells Mark what Trump uploaded in Content version `V1.1.1`.

This handoff is informational only. The single Source of Truth is:

`asset-history/asset_version_history.json`

Mark must build Pack JSON/manifests from History. Do not scan or copy physical
asset folders to infer Pack membership.

## Upload Summary

| Language | Type | Asset count | Size (bytes) |
|---|---|---:|---:|
| Chinese (`zh`) | audio | 1,093 | 41,439,136 |
| Japanese (`ja`) | audio | 1,000 | 14,517,685 |
| **Total** | **audio** | **2,093** | **55,956,821** |

Upload date: `2026-08-29`

Content version: `V1.1.1`

Upload commit:
`5b2ff95b6b78ab741fe25bddcb6ce8ea4ee6b1e7`

## GitHub Locations

- ZH: `assets/AUDIO-CONTENT-01/audio/zh/{d-prefix}/zh_{wordId}.aac`
- JA: `assets/AUDIO-CONTENT-01/audio/ja/{d-prefix}/ja_{wordId}.aac`

Examples:

- `assets/AUDIO-CONTENT-01/audio/zh/dAA/zh_dAA001.aac`
- `assets/AUDIO-CONTENT-01/audio/ja/dAA/ja_dAA001.aac`

Raw History URL:

`https://raw.githubusercontent.com/henryphu79-hash/EnglishPicture-Content/main/asset-history/asset_version_history.json`

## History Selection Contract

For this delivery, Mark must select records where:

```text
version == "V1.1.1"
type == "audio"
language in {"zh", "ja"}
```

Expected result:

```text
ZH records: 1,093
JA records: 1,000
Total records: 2,093
```

Each selected History record contains:

```json
{
  "assetId": "...",
  "wordId": "...",
  "type": "audio",
  "language": "zh|ja",
  "version": "V1.1.1",
  "uploadDate": "2026-08-29",
  "githubPath": "...",
  "sha256": "..."
}
```

Use `githubPath` as the asset location and `sha256` for integrity validation.
Do not derive either value from filenames or directory scanning.

## Validation Completed by Trump

- All 2,093 filenames match the language/word-ID naming standard.
- All 2,093 word IDs exist in the current dictionary.
- No duplicate `assetId` values were found.
- No zero-byte source files were found.
- All local target SHA-256 values match their History records.
- Raw History returned HTTP 200 after push.
- Remote sample files for the first and last ZH/JA records returned HTTP 200
  and matched their recorded SHA-256 values.

## Scope Boundary

Trump uploaded assets and appended History only.

The following were intentionally not changed:

- Pack JSON
- Pack manifests
- Global manifest
- Registry
- Dictionary
- Runtime
- Update Center

Mark owns the next step: create the Pack JSON/manifest from the selected History
records according to the approved content-delivery workflow.
