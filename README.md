# Iran Administrative Divisions / ایران



## Overview

| Item | Details |
|------|---------|
| Province | 31 |
| County | 429 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/ir](https://openadmindata.org/ir/) |
| API | [openadmindata.org/api/ir](https://openadmindata.org/api/ir/) |
| Flag | [PNG](https://onlygames.me/flags-png/ir/) · [SVG](https://onlygames.me/flags-svg/ir/) · [PDF](https://onlygames.me/flags-pdf/ir/) |
| National Anthem | [🎵 Listen & Download Iran National Anthem MP3](https://onlygames.me/national-anthems/ir/) |

## Browse by Province

| # | Province | Countys | Link |
|---|----|----|------|
| 1 | البرز (Alborz) | 6 | [Browse](divisions/alborz-ir001/) |
| 2 | اردبیل (Ardabil) | 10 | [Browse](divisions/ardabil-ir002/) |
| 3 | بوشهر (Bushehr) | 10 | [Browse](divisions/bushehr-ir003/) |
| 4 | چهارمحال و بختیاری (Chaharmahal and Bakhtiari) | 9 | [Browse](divisions/chaharmahal-and-bakhtiari-ir004/) |
| 5 | آذربایجان شرقی (East Azerbaijan) | 20 | [Browse](divisions/east-azerbaijan-ir005/) |
| 6 | فارس (Fars) | 29 | [Browse](divisions/fars-ir006/) |
| 7 | گیلان (Gilan) | 16 | [Browse](divisions/gilan-ir007/) |
| 8 | گلستان (Golestan) | 14 | [Browse](divisions/golestan-ir008/) |
| 9 | همدان (Hamadan) | 9 | [Browse](divisions/hamadan-ir009/) |
| 10 | هرمزگان (Hormozgan) | 13 | [Browse](divisions/hormozgan-ir010/) |
| 11 | ایلام (Ilam) | 10 | [Browse](divisions/ilam-ir011/) |
| 12 | اصفهان (Isfahan) | 24 | [Browse](divisions/isfahan-ir012/) |
| 13 | کرمان (Kerman) | 23 | [Browse](divisions/kerman-ir013/) |
| 14 | کرمانشاه (Kermanshah) | 14 | [Browse](divisions/kermanshah-ir014/) |
| 15 | خوزستان (Khuzestan) | 27 | [Browse](divisions/khuzestan-ir015/) |
| 16 | کهگیلویه و بویراحمد (Kohgiluyeh and Boyer-Ahmad) | 8 | [Browse](divisions/kohgiluyeh-and-boyer-ahmad-ir016/) |
| 17 | کردستان (Kurdistan) | 10 | [Browse](divisions/kurdistan-ir017/) |
| 18 | لرستان (Lorestan) | 11 | [Browse](divisions/lorestan-ir018/) |
| 19 | مرکزی (Markazi) | 12 | [Browse](divisions/markazi-ir019/) |
| 20 | مازندران (Mazandaran) | 22 | [Browse](divisions/mazandaran-ir020/) |
| 21 | خراسان شمالی (North Khorasan) | 8 | [Browse](divisions/north-khorasan-ir021/) |
| 22 | قزوین (Qazvin) | 6 | [Browse](divisions/qazvin-ir022/) |
| 23 | قم (Qom) | 1 | [Browse](divisions/qom-ir023/) |
| 24 | خراسان رضوی (Razavi Khorasan) | 28 | [Browse](divisions/razavi-khorasan-ir024/) |
| 25 | سمنان (Semnan) | 8 | [Browse](divisions/semnan-ir025/) |
| 26 | سیستان و بلوچستان (Sistan and Baluchestan) | 19 | [Browse](divisions/sistan-and-baluchestan-ir026/) |
| 27 | خراسان جنوبی (South Khorasan) | 11 | [Browse](divisions/south-khorasan-ir027/) |
| 28 | تهران (Tehran) | 16 | [Browse](divisions/tehran-ir028/) |
| 29 | آذربایجان غربی (West Azerbaijan) | 17 | [Browse](divisions/west-azerbaijan-ir029/) |
| 30 | یزد (Yazd) | 10 | [Browse](divisions/yazd-ir030/) |
| 31 | زنجان (Zanjan) | 8 | [Browse](divisions/zanjan-ir031/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 31 province records |
| [all-county.json](data/all-county.json) | JSON | All 429 county records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['county']} countys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=county |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
```

Countys are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Iran Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/iran-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
