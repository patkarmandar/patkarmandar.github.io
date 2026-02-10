+++
title = "Hosts Script — Unified Hostlist Generator"
date = 2021-06-15
description = "Hosts Script is a Bash-based utility that generates a unique, sorted, and consolidated hosts blocklist from multiple sources."
github = "https://github.com/patkarmandar/Hosts" # Optional
demo = "" # Optional
tags = ["bash", "tool", "adblock"]
categories = ["script"]
featured = false
+++

Hosts Script is a Bash-based utility that generates a unique, sorted, and consolidated hosts blocklist from multiple sources.

It supports combining:
- Existing hosts-formatted lists
- Plain domain/IP lists

The output can be directly used as a system `hosts` file or as an input for DNS-based blocking solutions.

### How It Works
- Fetches multiple hostlist sources defined by the user
- Normalizes domains into a hosts-style format
- Removes duplicates
- Sorts entries for consistency
- Redirects all blocked domains to a configurable local address (default: `0.0.0.0`)

The script helps maintain a clean, minimal, and deterministic blocklist from multiple upstream sources.

### Features
- Merge multiple hostlist sources
- Deduplicate and sort entries
- Generate hosts-formatted blocklists
- Configurable redirect IP
- Simple plain-text configuration
- Lightweight and dependency-free (Bash only)

### Configuration
| Parameter       | Description                                               |
| --------------- | --------------------------------------------------------- |
| `LOCAL_HOST`    | Local IP to redirect blocked domains (default: `0.0.0.0`) |
| `OUTPUT_HOST`   | Output file name (default: `hosts.txt`)                   |
| `source.list`   | Hosts-formatted sources                                   |
| `source.domain` | Plain domain/IP sources                                   |

#### Source File Format
`source.list`
Hosts-formatted entries only:
```
0.0.0.0 www.example.com
0.0.0.0 www.evil.com
```
`source.domain`
Domain or IP only:
```
www.example.com
www.evil.com
```

{{< alert type="important" >}}
If a source file contains only one entry, add an extra empty line at the end (known script limitation).
{{< /alert >}}

### Usage
1. Clone the Repository
    ```bash
    git clone https://github.com/patkarmandar/Hosts
    cd Hosts
    ```
2. Add Source Lists
    - Add hosts-formatted sources or links to `source.list`
    - Add plain domains/IPs or links to `source.domain`
    - One entry per line
3. Run the Script
    ```bash
    bash generate.sh
    ```
4. Output
    - The generated hosts blocklist will be available as: `hosts.txt`
5. You can append or replace it in:
    - `/etc/hosts` (Linux/macOS)
    - System DNS or Pi-hole
    - Custom DNS filtering tools

### Curated Hosts Lists
| Category  | Description               |
| --------- | ------------------------- |
| Porn      | Porn sites + ads          |
| Trackers  | MIUI & Microsoft trackers |
| Facebook  | Facebook domains          |
| Google    | Google domains            |
| Instagram | Instagram domains         |
| LinkedIn  | LinkedIn domains          |
| Twitter   | Twitter/X domains         |
| WhatsApp  | WhatsApp domains          |

### Credits & Sources

This project aggregates and processes data from the following sources:
- Steven Black Hosts
- Pornaway
- Fanboy Hosts
- Energized.pro
- LukeSmithxyz Hosts

{{< alert type="note" >}}
All credit goes to the original maintainers of these lists.
{{< /alert >}}

## Use Cases
- System-level ad blocking
- Privacy hardening
- DNS sinkhole input (Pi-hole, AdGuard)
- Social media blocking
- Tracker & telemetry reduction
