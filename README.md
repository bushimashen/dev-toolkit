# Dev Toolkit · 开发者工具箱

> 18 everyday developer utilities crammed into one HTML file. Zero dependencies, works offline, every computation happens in your browser — nothing is uploaded.

**English** | [简体中文](README.zh-CN.md)

<a href="https://bushimashen.github.io/dev-toolkit/"><b>▶ Live demo</b></a>

## What's inside

| # | Tool | Notes |
|---|---|---|
| 1 | JSON format / validate | Format, minify, escape and unescape; parse errors carry line and column |
| 2 | Base64 encode / decode | UTF-8 safe (Chinese text survives), plus URL-safe variant |
| 3 | URL encode / decode | `encodeURIComponent` / `decodeURIComponent` / `encodeURI` |
| 4 | JWT decode | Shows header and payload, flags expiry (signature is not verified) |
| 5 | Timestamp ↔ date | Seconds or milliseconds auto-detected; local, ISO and UTC output |
| 6 | UUID generator | v4, up to 200 at a time |
| 7 | Password generator | Pick length and character set, backed by the crypto RNG |
| 8 | MD5 | Pure-JS implementation, synchronous |
| 9 | SHA-1 / 256 / 512 | Uses Web Crypto (needs https or localhost) |
| 10 | Regex tester | Live match list with capture groups |
| 11 | Text diff (line by line) | LCS-based, outputs `+` / `-` |
| 12 | Radix conversion | Base 2–36 both ways; big numbers go through string math |
| 13 | Naming convention converter | camel / Pascal / snake / kebab / CONSTANT in one go |
| 14 | HTML / JSON escape | Both directions |
| 15 | Color conversion | HEX / RGB / HSL plus relative luminance |
| 16 | Crontab explainer | Translates to plain language and lists the next 5 runs |
| 17 | chmod calculator | Numeric ↔ `rwxr-xr-x` both ways |
| 18 | Text statistics | Characters, chars without spaces, CJK count, words, lines, paragraphs, UTF-8 bytes |

The left-hand list is searchable, and every tool shares the same input → output → copy flow.

## Usage

Download `index.html` and double-click it. No install, no build, no network.

Prefer a local server?

```bash
python -m http.server 8000
# then open http://localhost:8000
```

> The SHA tools rely on `crypto.subtle`, which some browsers disable under `file://`. If you see an "unsupported" message, open it through the local server above.

## Implementation notes

- **Zero dependencies** — every algorithm is inlined, including MD5, LCS line diff, cron parsing, big-number radix conversion and redmean color distance.
- **Deterministic** — password and UUID generation use the `crypto` RNG; MD5 and diff are pure functions you can lift out and reuse.
- **No uploads** — the file makes no network requests at all; `fetch` is not used anywhere.

## License

MIT — see [LICENSE](LICENSE).
