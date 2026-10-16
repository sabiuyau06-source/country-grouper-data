# Country Grouper – data

Public data used by the **Country Grouper** apps (Windows and Android).

## `nigeria_visa.json`
Entry rules for holders of an **ordinary Nigerian passport** in every country, plus a history of
visa changes and agreements (with sources). The apps download this file when they open,
update themselves and notify the user about new changes.

It is checked and updated **automatically every day** by a scheduled research task that looks for
new visa agreements or rule changes involving Nigeria, confirms them with official or reputable
sources, and records them here.

Fields:
- `version` – goes up by 1 every time the file changes (apps use this to detect updates)
- `updated` – date of the last change (YYYY-MM-DD)
- `countries` – `{ "Country": { "status": "...", "days": 90, "note": "..." } }`
  - `status` is one of: `visa-free`, `visa on arrival`, `eta`, `e-visa`, `visa required`, `restricted` (visas suspended), `no admission`
- `changes` – newest news first in the apps: `id`, `date`, `country`, `type`
  (`status-change`, `upcoming`, `agreement`, `info`), `from`, `to`, `title`, `details`, `source`, `source_name`

Baseline: Wikipedia "Visa requirements for Nigerian citizens" (2026) and the MIT-licensed
[passport-index-dataset](https://github.com/ilyankou/passport-index-dataset).

**Always confirm with the embassy before travelling.**
