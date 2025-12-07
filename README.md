# About
This package is an asynchronous API "wrapper" for retrieving data from iRacing. We use the term "wrapper" loosely as iRacing does not yet have an officially documented API; However, we've done our best to build something that might resemble one.

The goal of this project is to provide access to iRacing stats in a manner that is convenient, flexible, and efficient. In using this package, if you find something in its design that goes against these goals, **we want to know.**

The contributors of this project use Discord as the primary means of communication; The [iRacing Open Wheel server](https://discord.gg/UwnhM7w) was created by the author of this project and hosts the channels for discussion there. When joining, please ask Jacob Anderson for the role to see the appropriate channels.

# Documentation & Discussion
All documentation for this project is available through the [Github Pages project site](https://esterni.github.io/pyracing/).

---

## Fork Information

This is a fork of [Esterni/pyracing](https://github.com/Esterni/pyracing) with additional league-focused methods and improvements.

### New Methods Added in This Fork

The following methods have been added to support additional league functionality:

| Method | Description |
|--------|-------------|
| `get_completed_session_info(subsession_id)` | Get detailed results for a completed session by subsession ID |
| `get_league_calendar_by_season(season_id, league_id)` | Get the calendar/schedule for a league season |
| `get_league_active_sessions(league_id, start_row, stop_row)` | Get currently active sessions for a league |
| `get_league_members(league_id, lower_bound, upper_bound)` | Get members of a league with pagination support |

### Modified Methods

| Method | Change |
|--------|--------|
| `league_seasons(league_id, include_inactive)` | Added `include_inactive` parameter to optionally retrieve inactive seasons (defaults to `True`) |

### Other Changes from Upstream

- Updated `httpx` dependency to `>=0.23.0` for better compatibility
- Updated httpx parameter from deprecated `allow_redirects` to `follow_redirects`
- Uses existing constants (`ct.mSite`, `ct.URL_SUBS_RESULTS`) instead of hardcoded URLs where available
- Added type hints to new methods for better IDE support
- Added proper docstrings with Args and Returns documentation
- Added null-safety checks to prevent crashes on empty responses

### Synced with Upstream

This fork includes all upstream changes as of December 2025, including:
- Base64 encoded password submission on login forms
- iRacing maintenance mode detection during authentication
- Various bug fixes and improvements

---

# Dependencies
[httpx](https://www.python-httpx.org/) >= 0.23.0
