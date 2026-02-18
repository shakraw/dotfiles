## Project
RikordaTouch — kiosk client application used by Rikorda scarl company to let photo retailers make orders on Rikorda remote servers.

## Stack
- Python 3.12, PyQt 6.9.x, PyQt6-WebEngine 6.9.x, PyInstaller 6.13.0, Pillow 11.3
- Database: SQLAlchemy + Alembic
- Auth: none
- Task queue: none
- Deployed on: none

## Structure
- extlibs/ — windows utility tools source code used within the code
- libs/ — locally used custom libraries
- nsis/ — NSIS files to make builds on Windows systems
- src/ — main source code directory
- src/assets/ — assets files (i.e. fonts, images, styles)
- src/GPConfTemplates/ — config files for embedded Getphoto4 (never edit this files!)
- src/devices/ — source code to handle device specific image file sources / retrievement
- src/migrations/ — migrations
- src/models/ — models
- src/rthooks/ — hook code to run on startup to fix older version issues
- src/tests/ — old manual test files (to be removed)
- src/ui/ — main UI source code
- src/utils/ — utility code
- src/wifi_uploader_app/ — Flask app to receive files from web upload
- test/ - files (mirrors src/ structure) - to use for new tests
- main.py - main file for RikordaTouch app
- uploader.py - main file for RikordaTouch Uploader app
- updater.py - main file for RikordaTouch Updater app
- build_rikorda.bat - script to make RikordaTouch builds on Windows systems
- build_rikorda.sh - script to make RikordaTouch builds on MacOS (Intel) systems
- build_fdd.bat - script to make FDDTouch builds on Windows systems
- build_fdd.sh - script to make FDDTouch builds on MacOS (Intel) systems
- requirements.txt

## Commands
- Dev: `python main.py`
- Test: `pytest -v`
- Lint: `ruff check .`
- Format: `ruff format .`
- Type check: `mypy src/`
- Migrate: `alembic upgrade head`

## Verification
After every change, run in this order:
1. `mypy src/` — fix type errors
2. `pytest` — fix failing tests
3. `ruff check .` — fix lint errors

## Conventions

## Don't
- Don't use `# type: ignore` without a comment explaining why
- Don't catch bare `Exception` — catch specific exceptions