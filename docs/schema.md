# Schema

## Root object

| Key | Type | Description |
|-----|------|-------------|
| `spectrum_outages_datasets` | `array` | List of outage report records |

## Record fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `created_at` | `string` (ISO 8601 UTC) | Yes | When the report was submitted, e.g. `2026-06-30T18:07:13Z` |
| `city` | `string` | Yes | City name associated with the report |
| `state` | `string` | Yes | US state or territory abbreviation, e.g. `FL`, `TX`, `NY` |
| `zip_code` | `string` | Yes | 5-digit US ZIP code |
| `service` | `string` | Yes | Affected service category (see values below) |
| `note` | `string` \| `null` | Yes | Optional free-text detail from the reporter; `null` if none |

## `service` values

| Value | Description |
|-------|-------------|
| `Internet` | Internet service outage |
| `TV` | TV service outage |
| `Phone` | Phone / voice service outage |
| `Internet+TV` | Combined internet and TV outage |
| `All` | All services affected |

## Example record

```json
{
  "created_at": "2026-06-30T17:55:13Z",
  "city": "Winter Garden",
  "state": "FL",
  "zip_code": "34787",
  "service": "Internet",
  "note": null
}
```

## Notes

- Timestamps are stored in UTC (`Z` suffix).
- `zip_code` is stored as a string to preserve leading zeros where applicable.
- `note` may contain user-generated text; sanitize before display in downstream applications.
- Records do not include internal database identifiers or severity scores.

## CSV mapping

CSV columns match JSON field names exactly:

`created_at`, `city`, `state`, `zip_code`, `service`, `note`

Empty CSV cells represent `null` for `note`.
