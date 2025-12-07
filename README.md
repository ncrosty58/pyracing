# pyracing

Fork of [Esterni/pyracing](https://github.com/Esterni/pyracing) — an async Python wrapper for iRacing data.

For full documentation, see the [upstream project site](https://esterni.github.io/pyracing/).

---

## Fork Changes

This fork adds **league-focused methods** and modernizes deprecated Python/httpx patterns.

### New Methods

| Method | Description |
|--------|-------------|
| `get_completed_session_info(subsession_id)` | Get results for a completed session |
| `get_league_calendar_by_season(season_id, league_id)` | Get league season schedule |
| `get_league_active_sessions(league_id)` | Get active sessions for a league |
| `get_league_members(league_id)` | Get league member list |

### Modified Methods

| Method | Change |
|--------|--------|
| `league_seasons(league_id, include_inactive=True)` | Added `include_inactive` parameter |

### Other Changes

- **httpx**: Updated to `>=0.23.0`; replaced deprecated `allow_redirects` with `follow_redirects`
- **Python 3.11+**: Replaced deprecated `asyncio.coroutine` / `get_event_loop()` with `asyncio.run()`
- **Python 3.12+**: Replaced deprecated `datetime.utcfromtimestamp` with timezone-aware alternative
- Added type hints, docstrings, and null-safety checks on new methods

---

## Install

\`\`\`bash
pip install git+https://github.com/ncrosty58/pyracing.git
\`\`\`

## Requirements

- Python ≥ 3.8
- [httpx](https://www.python-httpx.org/) ≥ 0.23.0
