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
