# IOM Planning Query Tool

A Python command-line tool for searching and querying Isle of Man planning applications via the [PlanningPortal.im](https://planningportal.im) API.

Search 81,000+ planning applications by address, postcode, parish, case officer, or application type.

## Installation

```bash
pip install requests
git clone https://github.com/matthewkeen/iom-planning-query.git
cd iom-planning-query
```

## Usage

```bash
# Search by address or postcode
python query.py --search "Ballasalla"
python query.py --search "IM9 3AQ"

# Search by parish
python query.py --parish "Malew"

# Search by application type
python query.py --type "extension"

# Get details for a specific application
python query.py --ref "24/00182/B"

# Filter by outcome
python query.py --parish "Douglas" --outcome "approved"

# Export results to CSV
python query.py --parish "Rushen" --output results.csv
```

## API

This tool uses the public [PlanningPortal.im](https://planningportal.im) API. Visit the site directly to search via the web interface, browse by map, or explore officer profiles and parish statistics.

**API base URL:** `https://api.planningportal.im`

## Data Coverage

- 81,000+ planning applications
- 24 Isle of Man parishes
- Applications from the 1990s to present
- Decision notices, conditions, supporting documents

## Examples

```python
import requests

# Search applications in a parish
resp = requests.get("https://api.planningportal.im/applications", params={
    "parish": "Malew",
    "limit": 10
})
applications = resp.json()
```

## Related

- [PlanningPortal.im](https://planningportal.im) — Full web interface
- [IOM Planning Statistics](https://github.com/matthewkeen/iom-planning-stats) — Data analysis and articles

## Contributing

Issues and pull requests welcome. Planning data is public record — better tools benefit everyone on the island.

## Licence

MIT
