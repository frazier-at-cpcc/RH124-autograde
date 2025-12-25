# RH124 Auto-Grade Lab Tools

One-line installer for the RH124 lab grading system with xAPI integration and custom lab support.

## Quick Install

```bash
curl -sSL https://raw.githubusercontent.com/frazier-at-cpcc/RH124-autograde/master/install.sh | bash
```

Then reload your shell:
```bash
source ~/.bashrc
```

## What It Does

- Wraps the existing `lab` command to capture grading results
- Reports grades to a Learning Record Store (LRS) via xAPI
- Includes 33 custom lab exercises for RH124 course practice
- Supports offline grading with local queue

## Usage

```bash
# First run prompts for your email
lab start <slug>

# Grade a lab (results sent to LRS automatically)
lab grade <slug>

# List available custom labs
lab custom-labs list

# Grade a custom lab
lab grade users-user

# View/modify configuration
lab xapi-config show
lab xapi-config email your@email.com
```

## Included Custom Labs

The installer includes practice labs for:
- User and group management
- File and directory operations
- Permissions and ownership
- Text editing and file searching
- Service management
- Network configuration
- And more...

Run `lab custom-labs list` to see all available labs.

## Uninstall

```bash
~/.local/share/lab-xapi/lab-xapi --uninstall
```

Or run the installer with the uninstall flag:
```bash
curl -sSL https://raw.githubusercontent.com/frazier-at-cpcc/RH124-autograde/master/install.sh | bash -s -- --uninstall
```

## Requirements

- RHEL/CentOS with the `lab` command installed (`/usr/local/bin/lab`)
- Python 3
- `requests` and `pyyaml` Python modules (auto-installed if missing)
