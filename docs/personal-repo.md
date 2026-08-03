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

## Personal Feed

The feed URLs in `scripts/prepare-digest.js` point to this repository:

- `feed-x.json`
- `feed-podcasts.json`
- `feed-blogs.json`
- `prompts/`

The GitHub Action generates feeds from `config/default-sources.json`. Configure
the repository secrets before enabling scheduled collection:

- `X_BEARER_TOKEN`
- `POD2TXT_API_KEY` for podcast transcription

The default schedule is 07:17 in `Asia/Shanghai`.

## Local Digest Flow

```bash
node scripts/prepare-digest.js --expanded > /tmp/ai-builders-digest.json
```

The prepare command returns the feed and remix prompts as JSON. After the digest
text has been assembled, pass the final Markdown file to `deliver.js` to export
it under `data/YYYY-MM-DD/`.

In this clean upstream baseline, `prepare-digest.js` reads the personal raw
GitHub URLs directly. The feed files are generated and committed by this
repository's GitHub Action, so the local digest flow does not silently use the
upstream central feed.
