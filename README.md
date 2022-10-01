# pixel7-config

Deployed configuration of the Google Pixel 7 (`panther`) for the Configuration
Control Dashboard (CCD) case study. The CCD reads this repo as the **actual
state** of software and firmware configuration items and compares it with the
approved baseline and the ECRs in Jira.

**Public-data case study.** Every version here comes from public sources
(Google factory images page, AOSP Gitiles, Pixel update bulletins). It is not
Google's internal configuration data.

- `device.yaml` - current build, Android version and security patch level per variant
- `software/<CI>/version.yaml`, `firmware/<CI>/version.yaml` - one folder per tracked CI
- Tags `build/<build_id>` - repo state when that real build shipped (history replayed by
  `ccd/sync/bootstrap_repo.py`, commit dates = release month)

To demo drift, edit a `version.yaml` (for example `firmware/FW-002_radio`) and commit
without an approved ECR in `cr:`.
