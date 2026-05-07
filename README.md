# Archive Trail

Smart launcher for archive and cache lookups. Paste a URL or handle, see thirty-one archives grouped by intent (recover, compare, regional), with jurisdiction-specific archives pinned to the top. Every pivot logged with a session ID for your case file. Citation-ready exports.

Live: https://signalandshadow.github.io/archive-trail/

Part of Signal & Shadow (signalandshadow.io). Built under SIG-ARC-001 and LST-001 v1.0.3.

## What it does

- **Smart entity detection.** Detects URLs, domains, and X/Twitter handles. Adapts the target list to what each archive accepts.
- **Intent grouping.** Three groups: recover (single-snapshot retrieval), compare (search engine caches), regional (national archives). Operational note on every row.
- **TLD pinning.** Paste a `.pt` URL and Arquivo.pt floats to the top of the regional group. `.gov.uk` pins UK Government Web Archive and PRONI. Cyrillic content surfaces Yandex and Mail.ru.
- **Batch open.** Tick the rows you want, hit Open batch. Browser opens one tab per archive.
- **Session log.** Every pivot timestamped, exportable as CSV or Markdown (with YAML frontmatter for Obsidian/Notion ingest).
- **Print to PDF.** Cmd/Ctrl+P generates a clean forensic report with the activity log.
- **SHA-256 of the URL** baked into the citation note and exports for evidence integrity.
- **Keyboard navigation.** `/` focuses search, arrows move between rows, Space toggles selection, Enter opens, Esc clears focus.

## What it does not do (yet)

- **No federated discovery.** v0.2 ships as a launchpad, not a verifier. The earlier prototype queried Memento and Wayback CDX in the browser, but Internet Archive's CORS posture is inconsistent and rate-limited at 60 requests per minute with escalating firewall bans. Verification returns in v0.3 once a Cloudflare Worker on `api.signalandshadow.io` is in place to bypass these constraints reliably.
- **No paywall bypass.** The tool fires search URLs; you confirm what each archive returns.
- **No new captures.** For saving a fresh snapshot, use Wayback's "Save Page Now" or Archive.today directly.

## Build

Single static HTML file. No build step. No network calls. Open `index.html` in a browser, or serve via any static host.

## Standards

- LST-001 v1.0.3 (editorial)
- SIG-STD-002 v2.0 (verification methodology)
- Berkeley Protocol aligned

## Roadmap

- v0.3: Federated discovery via Cloudflare Worker proxy
- v0.4: Per-archive endpoint research for the manual-check rows
- v0.5: Side-by-side snapshot compare view

## Licence

MIT. Use it, fork it, audit it.
