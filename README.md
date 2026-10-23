# Attendance Alchemist

**Your report. A little abracadabra with Python. Attendance, sorted.**

A small desktop app that turns SLCM's Date Wise Attendance Report into a clear
Excel attendance workbook, without manual column mapping.

## Download

[Download the Linux app](https://github.com/lijomjose/attendance-alchemist/releases/latest)

| Platform | Availability |
|---|---|
| Linux, Intel/AMD 64-bit | Ready standalone executable; Ubuntu 24.04+ / glibc 2.39+ |
| Windows | Executable not yet available; a native Windows build is required |

For Linux, extract the ZIP, allow `AttendanceAlchemist` to run as a program in
its file properties, and open it. Python does not need to be installed.
If using a terminal:

```bash
chmod +x AttendanceAlchemist
./AttendanceAlchemist
```

The executable is also in [`downloads/linux`](downloads/linux).

## Get your SLCM report

**Shortcut:** log in to SLCM first, then try
[opening the report directly](https://maheslcmtech.lightning.force.com/lightning/r/sObject/00OOS0000028M0b2AE/view?queryScope=userFolders).

If the link does not work:

1. Log in to SLCM and go to **Reports**.
2. Search for **Copy of Date Wise Attendance Report** and open it.
3. Click the **down arrow beside Edit**, then select **Export**.
4. Save the exported XLSX, ODS or CSV file.

In the app, choose that file, optionally choose an output location, and click
**Work your magic — Generate sheets**. These instructions and the direct link
are also available under **Where do I find the report?**

Then be happy. You can thank me later!

## What you get

- One worksheet per subject and section.
- Serial number, student name and chronological date-only session columns.
- Cumulative present counts: `1, 2, A, 3, A, 4`.
- Total classes at the top and attendance percentage in the final column.
- Local processing; student data is not uploaded by the app.

## Details that affect the numbers

The app expects the standard portal report format. It identifies students by
exact name within the full course offering because this export has no student
registration numbers. Two students with the same name in one class cannot be
distinguished by this report.

Sessions on the same day remain separate using their reported start times,
although only the dates appear in the output. Identical duplicate attendance
records count once; contradictory duplicates stop conversion. Missing records
stay blank. Attendance percentage is present sessions divided by the total
sessions for that class. Each session record counts as one attendance unit.

The app reads the first input worksheet and skips portal subtotals and footers.
It preserves the source report and replaces an existing output at the chosen
save path only after successful conversion.

## Version 1.2.0

Includes the Attendance Alchemist branding, author credit in the app footer,
the login-first report shortcut and manual download instructions.
The Linux packaged converter has passed a synthetic smoke test; source tests
also cover 20,000 attendance records. GUI appearance has not been tested on
every Linux desktop.

The downloadable package contains the app and instructions. No real attendance
reports or student workbooks are included.
