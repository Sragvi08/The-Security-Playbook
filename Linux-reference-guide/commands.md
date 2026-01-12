# Linux Command Reference Guide

---

## find — Search for Files and Directories

### Description
The `find` command is used to search for files and directories based on various criteria such as name, type, size, ownership, and timestamps. It is heavily used in Linux administration, CTFs, and penetration testing scenarios.

---

### Basic Syntax
```bash
find [directory] [options]
find /home/Andy -type f -name sales.txt
```
-type f → search for files only
-name → case-sensitive filename match

Find directories by directory name
```bash
find /home/Andy -type d -name pictures
```
-type d → search for directories only

Find files by size
```bash
find /home/Andy -type f -size 10c
```

Size units:
- c → bytes
- k → kilobytes
- M → megabytes
- G → gigabytes

Find files by owner (user)
```bash
find /etc/server -type f -user john
```
Find files by group
```bash
find /etc/server -type f -group teamstar
```
Find files modified after a specific date
```bash
find / -type f -newermt '2020-06-30 00:00:00'
```

Matches files modified after the specified date and time

Find files modified within a date range
```bash
find / -type f -newermt 2013-09-12 ! -newermt 2013-09-14
```
- Excludes files modified before 2013-09-12
- Excludes files modified after 2013-09-14
- Matches files modified on 2013-09-13 only

Find files accessed within a date range
```bash
find / -type f -newerat 2017-09-12 ! -newerat 2017-09-14
```
Find files containing a specific keyword
```bash
grep -iRl 'flag' /folderA
```
- i → case-insensitive search
- R → recursive search
- l → display filenames only

Suppress permission denied errors
```bash
find / -type f 2>/dev/null
```

Redirects error output to /dev/null to reduce noise

--- 

Helpful Tips
- Read the full manual: man find
- Clear the terminal quickly: Ctrl + L
- Reuse the last command: ↑ (Up Arrow)

---
Security / CTF Relevance
- Locate sensitive files (configs, credentials, flags)
- Enumerate files owned by specific users or groups
- Identify recently modified or accessed files
- Combine with grep, xargs, and output redirection for powerful enumeration
