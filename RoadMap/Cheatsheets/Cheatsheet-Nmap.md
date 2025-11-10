<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [📡 Nmap Cheatsheet](#-nmap-cheatsheet)
  - [Basic Scans](#basic-scans)
  - [Save Results](#save-results)
  - [Common Flags](#common-flags)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 📡 Nmap Cheatsheet

## Basic Scans
- `nmap -sC -sV <target>` → default scripts & version
- `nmap -A <target>` → aggressive scan
- `nmap -p- <target>` → all ports

## Save Results
- `nmap -oN scan.txt <target>` → normal output
- `nmap -oX scan.xml <target>` → XML output

## Common Flags
- `-Pn` → skip host discovery
- `-T4` → faster timing
- `-sU` → UDP scan
