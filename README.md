[update-readmes]   Mode: rewrite — migrating to template structure...
# brickstorm-scanner

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/brickstorm-scanner)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/brickstorm-scanner.git
cd brickstorm-scanner
```

## Usage


You can download the standalone Bash script (`find_brickstorm.sh`) directly
from this repository.

The IoC Scanner can be run directly on a Linux or BSD-based appliance or system. The
tool writes diagnostic messages to STDERR and results (matches) to STDOUT. In
typical usage, you should redirect STDOUT to a file for review. The tool must be
run with execute permissions.

**1. Make the script executable**:
```
chmod +x ./find_brickstorm.sh
```

**2. Scan an entire directory recursively**: The script will use `find` to scan
all files within the specified directory. BRICKSTORM has been deployed to a variety of locations on appliances and Mandiant recommends a thorough review of the entire file system.
**note:** This script will traverse all mounted filesystems. If you are running this script on a device with large datastore volumes, take care to specify paths that exclude them. 

```
./find_brickstorm.sh -o logfile.txt /directory/to/scan/
```

### Interpreting Results

The tool will output `MATCH: <filepath>` to STDOUT for any file that meets all
three criteria. The output will be the full path to the file.

**Example Output**:

```
MATCH: /usr/bin/vami-lighttp
MATCH: /tmp/pg_update
```

If the scanner identifies a potential match, organizations should
perform a forensic examination of the compromised system to determine the scope
and extent of the incident. Contact investigations at mandiant dot com if you have questions or need assistance.

### Design

We provide this tool as a Bash script because it's a common denominator across
many Linux-based appliances (from vendors like VMware, Ivanti, and others) that
may not have YARA or other security tools installed. It uses common, built-in
utilities like `grep, xxd, head, sed`, and `find` to perform its checks.

### Further Reading

For additional information from Mandiant and Google Threat Intelligence Group (GTIG) regarding BRICKSTORM and in-the-wild
exploitation, please see:

- https://cloud.google.com/blog/topics/threat-intelligence/brickstorm-espionage-campaign - Published on September 24, 2025

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/brickstorm-scanner`](https://github.com/Interested-Deving-1896/brickstorm-scanner) and mirrored through:

```
Interested-Deving-1896/brickstorm-scanner  ──►  OpenOS-Project-OSP/brickstorm-scanner  ──►  OpenOS-Project-Ecosystem-OOC/brickstorm-scanner
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
