# Archive Trail

Federated archive discovery for OSINT investigators. Paste a URL, see which archives have a snapshot before you click. Every pivot logged with the snapshot's Memento-Datetime. Citation-ready exports.

Live: https://signalandshadow.github.io/archive-trail/

Part of Signal & Shadow (signalandshadow.io). Built under SIG-ARC-001 and LST-001 v1.0.3.

## What it does

Queries the Memento federated aggregator and the Wayback Machine CDX API in the background when you paste a URL. Reports per-archive snapshot counts and date ranges in real time. The eight Memento-covered archives (Wayback, Archive.today, UK Web Archive, Library of Congress, Stanford, Trove, Arquivo.pt, Versafn.is) get verified counts. The remaining archives get honest "manual check" labelling: the tool fires the search URL, but you confirm the result.

## What it does not do

- It does not bypass paywalls or login walls.
- It does not save snapshots itself. For new captures, use Wayback Machine's "Save Page Now" or Archive.today directly.
- It does not proxy any requests through a third-party server. All network calls go direct from your browser to the archive.

## Output

- Activity log of every pivot, exportable as CSV or Markdown (with YAML frontmatter for Obsidian/Notion ingest)
- Print to PDF for paper case files
- Citation note with session ID, target hash, and pivot count, ready to drop into a report

## Build

This is a single static HTML file. No build step. To run locally, serve it via a local web server (federated discovery requires HTTPS; opening the file directly via `file://` will block API calls).

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## Standards

- LST-001 v1.0.3 (editorial)
- SIG-STD-002 v2.0 (verification methodology)
- Berkeley Protocol aligned

## Licence

MIT. Use it, fork it, audit it.
