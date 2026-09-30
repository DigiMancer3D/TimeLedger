# #TimeLedger v0.1.0

## A portable, local-first time ledger for attractions, events, guest services, and shift-based teams

#TimeLedger is a privacy-respecting, local-first time and attendance system built for attractions, tours, events, guest-service operations, seasonal venues, and similar workforce teams. It is designed to work entirely on the device you are using—without cloud storage, no login to a hosted backend, and no dependence on an always-online service.

This public release is a genericized version of an internal venue-management tool, rebuilt for broader use and easier adoption by other operators who want a simple, transparent, offline-first system.

---

## Why #TimeLedger?

- Local-first design: works online or offline
- No server required: runs directly from your browser
- Portable data model: save and restore state via `.wps` and HTML snapshots
- Built for shift operations: clock in/out, manual correction, roster management, exports
- Practical for attractions and event teams: attendance, role tracking, scheduling, payroll-friendly outputs
- Easy to share: generate portable state links using itty.bitty by Alcor

---

## Quick start

1. Open `TimeLedger_Manager.html` for the full configuration and management experience.
2. Open `TimeLedger_Employee.html` for a cleaner employee/front-desk clock view.
3. In Manager Setup, set your organization name and update categories/positions to fit your operation.
4. Build your roster and add employees.
5. Start clocking in and out.
6. Export CSV/PNG or download a local `.wps` backup when needed.

Note: The default organization is `Attraction Organization`, and the default public logo is `TimeLedgerLogo.png`. Keep that image beside the HTML files so the default branding loads correctly.

---

## Core features

### Local-first and offline-ready
- Works without a server or authentication backend
- Keeps data in the browser and on local files
- Offline copy support for self-contained backups
- Portable state exports for continuity and transfer

### Manager + employee workflows
- Manager setup and configuration screens
- Employee roster editing and role assignment
- Manual clock entries with provenance markers
- Batch clocking across multiple employees
- Manager attribution on entries and exports

### Payroll and reporting support
- Custom spreadsheet layouts
- Attraction Timesheet preset for common venue reporting
- CSV export for payroll and spreadsheet workflows
- PNG export for easy visual verification
- Full ledger review with event editing

### Shareable state links
- Generate portable links for employees or saved state snapshots
- Uses compressed HTML state embedded in a URL
- Works with itty.bitty by Alcor for shareable, lightweight link packaging

---

## itty.bitty by Alcor integration

#TimeLedger includes portable state-sharing workflows designed to work well with [itty.bitty](https://itty.bitty.app) by [Alcor](https://github.com/alcor).

This is a strong fit for local-first tools because the app can package a compressed version of its state into a URL and send that link to another device. That makes it possible to:

- generate an employee-facing page for a safe, minimal workflow
- share a current state snapshot with a manager or team member
- archive a version of the ledger without needing a hosted database
- move between devices without a central server

The result is a practical, lightweight distribution model that preserves the app's local-first philosophy while still making sharing easy.

---

## Generic attraction presets

The default roster categories are written in broad attraction-industry terms rather than one specific venue's language:

- Attraction Operations — Attraction Attendant, Attraction Operator, Queue Attendant, Guest Flow Attendant, Attraction Lead, Attraction Manager
- Attraction Tours — Tour Guide, Tour Host, Presenter, Tour Assistant, Tour Lead, Tour Manager
- Guest Services — Admissions, Ticketing, Front Desk, Guest Services, Lead, Manager
- Entertainment & Events — Performer, Character Performer, Event Host, Presenter, Stage / Show Crew, Lead, Manager
- Food & Beverage — Food Service Staff, Cook, Server, Host, Lead, Manager
- Facilities & Safety — Maintenance, Facilities, Custodial, Security, Safety Attendant, Lead, Manager
- Support Staff — Administrative, Marketing, Merchandise, Online Orders, Technical Support, Web / Media, Artist / Fabrication, Props / Set Support

All categories and positions are editable from the Manager Setup screen.

---

## Attraction Timesheet preset

The public release includes a genericized manager export profile called **Attraction Timesheet**. Its default fields are:

`Name | Department | Handbook | Orientation | Safety Training | Role Training | Total Hrs`

This is intended for seasonal or attraction-style operations that need a simple, payroll-friendly view of staffing, verification, and training status.

Managers can add optional training/rehearsal dates and scheduled event dates, then press **Rebuild Attraction Timesheet Dates** to generate the relevant date columns before exporting.

The legacy `autoboss` key and owner verification keys are retained for compatibility with earlier alpha.14 `.wps` state files and CSV field maps.

---

## Export and continuity behavior

- Curb Verification Data defaults to ON. With it ON, exports only the selected spreadsheet fields.
- With it OFF, TimeLedger adds a `Verification Data` section and protected `Field Map JSON` data.
- Routine CSV/PNG export only sends new-to-export ledger rows; full history remains available in `.wps`, Offline Copy, state links, and the manager ledger.
- Manager PNG export mirrors the same export table used by CSV and includes visible role, manager, export time, profile, and verification status.
- The app keeps local provenance evidence in the form of manager names and integrity hashes.

---

## Compatibility and privacy

This public package intentionally excludes the private historical payroll workbook and all private venue-specific logos, dates, categories, and names. The `.wps` format and internal `WPS-Time-Ledger` state structure are retained for continuity with earlier builds.

Before sharing real workforce exports, remember that CSV, PNG, and `.wps` files can contain names, work times, manager attribution, custom fields, and other employment data. Always review what you are exporting before sending it anywhere.

---

## Files included

- `TimeLedger_Manager.html` — full manager application
- `TimeLedger_Employee.html` — simplified employee/front-desk interface
- `TimeLedgerLogo.png` — default public logo
- `docs/Owner_Operations_Guide.pdf` — owner/operations overview
- `docs/Manager_Guide.pdf` — manager workflow guide
- `docs/Employee_Quick_Guide.pdf` — employee quick guide
- `MANUAL_ACCEPTANCE_CHECKLIST.md` — release validation checklist
- `TEST_REPORT.txt` — automated test summary
- `PUBLIC_RELEASE_NOTES.md` — release and compatibility notes
- `SHA256SUMS.txt` — release file checksums
- `scripts/verify_release.sh` — structural and JavaScript verification
- `tests/` — optional Playwright acceptance tests
- `examples/Attraction_Timesheet_SAMPLE.csv` — sample data only

---

## Open-source note

This package does not add a software license on the author's behalf. Add the license you want to the repository before describing the project as open-source under a specific license.

---

## Recommended use cases

#TimeLedger is especially well-suited to:

- attractions and theme parks
- tours and guided experiences
- event staffing and front-of-house teams
- seasonal operations and pop-up venues
- hospitality check-in/check-out operations
- volunteer or support staffing rosters
- guest-service teams with variable shift patterns

---

## Summary

#TimeLedger is a practical, transparent, and flexible local-first time ledger designed for real operations. It keeps the essentials simple—clocking, roster management, exports, and local backups—while remaining adaptable to the way different venues and teams actually work.

With its local-first model, portable share workflows, and compatibility with itty.bitty by Alcor, it offers a lightweight alternative to traditional workforce software without giving up control of the data.

---

Ready to get started? Open `TimeLedger_Manager.html` and begin setting up your organization.
