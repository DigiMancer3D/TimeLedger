# #TimeLedger v0.1.0 - 0.1.0-alpha.14-public.1

#TimeLedger is a portable, local-first time ledger for attractions, tours, events, guest-service operations, seasonal venues, and similar teams. This public build is the genericized release of the tested alpha.14 venue-specific implementation: the application mechanics are retained while venue names, seasonal dates, private reference data, and attraction-specific terminology are removed.

## Start here

- Open `TimeLedger_Manager.html` for setup, roster management, supervised clocking, imports, full-ledger review, and exports.
- Open `TimeLedger_Employee.html` for a simpler employee/front-desk clock view.
- The default organization is `Attraction Organization`; change it in Manager Setup.
- The default public logo setting is `TimeLedgerLogo.png`, matching the logo already stored in the public GitHub repository. Keep that image beside the HTML files. If it is unavailable, the page falls back to a `#TL` text mark.

## Generic attraction presets

The factory roster categories intentionally use common attraction-industry terms rather than one venue's terminology:

- **Attraction Operations** - Attraction Attendant, Attraction Operator, Queue Attendant, Guest Flow Attendant, Attraction Lead, Attraction Manager.
- **Attraction Tours** - Tour Guide, Tour Host, Presenter, Tour Assistant, Tour Lead, Tour Manager.
- **Guest Services** - Admissions, Ticketing, Front Desk, Guest Services, Lead, Manager.
- **Entertainment & Events** - Performer, Character Performer, Event Host, Presenter, Stage / Show Crew, Lead, Manager.
- **Food & Beverage** - Food Service Staff, Cook, Server, Host, Lead, Manager.
- **Facilities & Safety** - Maintenance, Facilities, Custodial, Security, Safety Attendant, Lead, Manager.
- **Support Staff** - Administrative, Marketing, Merchandise, Online Orders, Technical Support, Web / Media, Artist / Fabrication, Props / Set Support.

All categories and positions are editable in Manager Setup.

## Attraction Timesheet preset

The former venue-specific payroll preset is presented publicly as **Attraction Timesheet**. Its factory fields are:

`Name | Department | Handbook | Orientation | Safety Training | Role Training | Total Hrs`

No private season dates are preloaded. A Manager can add an optional training/rehearsal date plus scheduled attraction dates, press **Rebuild Attraction Timesheet Dates**, then **Change Spreadsheet**. Date columns aggregate new-to-export hours by employee and date.

The old internal `autoboss` key and `owner_scare_101/201/301` state keys are deliberately retained for backward compatibility with alpha.14 `.wps` state and CSV field maps. Public UI labels are generic, and CSV import accepts both the old headers and the new `Orientation`, `Safety Training`, and `Role Training` headers.

## Export / continuity behavior

- **Curb Verification Data** defaults ON. ON exports only the selected spreadsheet fields; OFF adds `Verification Data` at the front and protected `Field Map JSON` at the end.
- Manager PNG export mirrors the same export table used by CSV and includes visible role, Manager, export time, profile, and verification-curb status.
- Routine CSV/PNG export sends only new-to-export ledger events; full history stays available in `.wps`, Offline Copy, state links, and the Manager ledger.
- TimeLedger is local-first/serverless-style. Manager names and integrity hashes are local provenance evidence, not remote identity authentication or tamper-proof proof against someone able to alter the HTML/JavaScript.

## Compatibility and privacy

The public package intentionally excludes the private historical payroll workbook and all private venue-specific logos, dates, categories, and names. The `.wps` extension and internal `WPS-Time-Ledger` schema identifier remain for compatibility; they are implementation identifiers, not public branding.

Before sharing real workforce exports, remember that CSV/PNG/.wps files can contain names, work times, manager attribution, pay-related custom fields, and other employment data you configure. Review files before publishing them.

## Files

- `TimeLedger_Manager.html` - full Manager application.
- `TimeLedger_Employee.html` - employee/front-desk application.
- `docs/Owner_Operations_Guide.pdf` - owner/operations overview.
- `docs/Manager_Guide.pdf` - Manager workflow.
- `docs/Employee_Quick_Guide.pdf` - clock-in/out quick guide.
- `MANUAL_ACCEPTANCE_CHECKLIST.md` - public-release manual test pass.
- `TEST_REPORT.txt` - automated test summary for this package.
- `PUBLIC_RELEASE_NOTES.md` - public-release changes and compatibility notes.
- `SHA256SUMS.txt` - release file checksums.
- `scripts/verify_release.sh` - structural and JavaScript verification.
- `tests/` - optional Playwright acceptance tests.
- `examples/Attraction_Timesheet_SAMPLE.csv` - synthetic sample data only.

## GitHub

Repository: https://github.com/DigiMancer3D/TimeLedger

The repository already contains `TimeLedgerLogo.png`; keep it at the repository root beside the two HTML applications so the default logo path resolves both on a normal web host and when the folder is served locally.

## License note

This package does not add a software license on the author's behalf. Add the license you want to the repository before describing the project as open-source under a particular license.
