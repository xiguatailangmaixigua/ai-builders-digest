# Personal Repository Notes

This repository is a personal, clean mirror of the upstream `follow-builders`
codebase. It keeps the feed generator and digest workflow, while storing the
historical digests separately under `data/YYYY-MM-DD/`.

## Migration Boundary

- Source code: cloned from `zarazhangrui/follow-builders`.
- Historical archive: 56 existing `digest*.md` files copied from the local
  working archive.
- Excluded: research folders, visual assets, experiments, temporary files,
  uncommitted source changes, and unrelated documentation.
- The archive contains rendered digest text, not the original X/API payloads
  for every date.

## Feed Mode

This repository currently uses the upstream central feed, so no X API token is
needed for local Digest generation. The feed URLs in `scripts/prepare-digest.js`
point to `zarazhangrui/follow-builders`:

- `feed-x.json`
- `feed-podcasts.json`
- `feed-blogs.json`
- `prompts/`

The `feed-*.json` files in this repository are snapshots copied during the
archive migration. They are not the active live source. The self-hosted feed
workflow is manual-only and is intentionally not scheduled.

To switch to self-hosted collection later, point the URLs back to this
repository, configure `config/default-sources.json`, and add these secrets:

- `X_BEARER_TOKEN`
- `POD2TXT_API_KEY` for podcast transcription

The upstream central repository remains responsible for the 07:17
`Asia/Shanghai` feed refresh.

## Local Digest Flow

```bash
node scripts/prepare-digest.js --expanded > /tmp/ai-builders-digest.json
```

The prepare command returns the feed and remix prompts as JSON. After the digest
text has been assembled, pass the final Markdown file to `deliver.js` to export
it under `data/YYYY-MM-DD/`.

`prepare-digest.js` reads the upstream raw GitHub URLs directly. The local
archive and its GitHub repository therefore do not silently require or use a
personal X API token.
