<p align="right">
  [English]
  [<a href="README-ko.md">한국어</a>]
</p>

# qsrm

> Quick and safe bulk removal tool – protect yourself from accidental deletes!

## Overview

`qsrm` is a Bash script that safely removes files and directories based on a list. By default, it runs in **dry-run mode**, ensuring nothing is deleted until explicitly confirmed.

- ✅ Dry-run mode by default
- ⚠️ Prompts before deletion
- 🔐 Path list-based deletion to prevent mistakes
- 🧹 Great for safe automation and cleanup

## Installation

```bash
chmod +x qsrm
mv qsrm /usr/local/bin/
```

## Usage

```bash
qsrm [-f] [-r] path_list.txt
```

## Options

| Option | Description                          |
| ------ | ------------------------------------ |
| `-f`   | Force deletion (no confirmation)     |
| `-r`   | Actually delete (default is dry-run) |

## Example

Write target paths to targets.txt (one per line):

```bash
/tmp/test1
~/Downloads/old_project
```

Preview without deletion (default):

```bash
qsrm targets.txt
```

Prompted actual deletion:

```bash
qsrm -r targets.txt
```

Force delete with no prompt:

```bash
qsrm -f -r targets.txt
```

## Sample Output

```yaml
[2025-07-18 11:00:00] Loading paths from: targets.txt
Total targets: 3
Dry-run mode ON
[DRY-RUN] Would delete: /tmp/test1
[DRY-RUN] Would delete: /tmp/test2
...

--- Summary ---
Total  : 3
Deleted: 3
```

## Recommendations

- Always run without -r first to preview.
- Be cautious with rm -rf, especially in scripts.

## License

MIT License