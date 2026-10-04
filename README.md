# Cybersecurity Roadmap

![License](https://img.shields.io/badge/license-MIT-green.svg) ![focus](https://img.shields.io/badge/focus-offense%20%2B%20defense-red.svg) ![rule](https://img.shields.io/badge/rule-authorized%20targets%20only-critical.svg)

Offensive and defensive security, built on labs you own and platforms that exist for practice. Understand how systems break so you can build and defend them.

## Table of Contents

1. [Workflow Overview](#workflow-overview)
2. [Prerequisites](#prerequisites)
3. [Phase 1: Foundations](#phase-1-foundations)
4. [Phase 2: Web Security](#phase-2-web-security)
5. [Phase 3: Cryptography](#phase-3-cryptography)
6. [Phase 4: Binary Exploitation & Reverse Engineering](#phase-4-binary-exploitation--reverse-engineering)
7. [Phase 5: Offense Practice](#phase-5-offense-practice)
8. [Phase 6: Defense & Detection](#phase-6-defense--detection)
9. [Capstone Projects](#capstone-projects)
10. [Repository Layout](#repository-layout)
11. [Engineering Rules](#engineering-rules)
12. [Exit Criteria](#exit-criteria)

---

## Workflow Overview

```
 Linux + CLI --> Web security --> Cryptography --> Binary / reverse engineering
                      |                                        |
                      v                                        v
              CTF + lab practice  <------------------>  Blue team + detection
                      |                                        |
                      +------------> Home lab capstone <------+
```

## Prerequisites

- [ ] Comfortable in Linux and the shell
- [ ] Networking basics (see the Networks and Cloud roadmap)
- [ ] Python scripting (Stage 1 of the ML roadmap)
- [ ] Read the authorization rule in Engineering Rules before any hands-on work

## Phase 1: Foundations

Goal: Operate comfortably in a shell and know the threat landscape.

| Resource | Type | Why |
|----------|------|-----|
| [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) | Wargame | Linux and shell fluency through puzzles |
| [The Linux Command Line](https://linuxcommand.org/tlcl.php) | Free book | Shell reference |
| [Security Engineering (Ross Anderson)](https://www.cl.cam.ac.uk/~rja14/book.html) | Free book | Threat models and why systems fail |
| [OWASP Top 10](https://owasp.org/www-project-top-ten/) | Reference | Most common web risks |
| [MITRE ATT&CK](https://attack.mitre.org/) | Knowledge base | Attacker tactics and techniques |

- [ ] Finish Bandit levels 0 to 20
- [ ] Security Engineering: chapters on protocols, access control, psychology
- [ ] Map each OWASP Top 10 item to a real breach

**Deliverables**
- [ ] `writeups/bandit.md`
- [ ] `docs/threat_model_template.md`

## Phase 2: Web Security

Goal: Find and exploit common web vulnerabilities in legal practice environments.

| Resource | Type | Why |
|----------|------|-----|
| [PortSwigger Web Security Academy](https://portswigger.net/web-security) | Free labs | Best hands-on web security material |
| [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) | Practice app | Deliberately vulnerable app you run locally |
| [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/) | Reference | Defensive fixes for each class |
| [Burp Suite Community Edition](https://portswigger.net/burp/communitydownload) | Tool | Intercepting proxy |

- [ ] Academy: SQL injection, XSS, CSRF, authentication, access control
- [ ] Solve 20 Juice Shop challenges
- [ ] For each bug class, write the vulnerable code and the fixed code

**Deliverables**
- [ ] `writeups/` entries for 15 Academy labs
- [ ] `labs/vuln_app/` with paired vulnerable and patched versions, plus tests

## Phase 3: Cryptography

Goal: Understand primitives well enough to use them correctly and recognize misuse.

| Resource | Type | Why |
|----------|------|-----|
| [Crypto 101](https://www.crypto101.io/) | Free book | Intro to real-world cryptography |
| [Serious Cryptography](https://nostarch.com/seriouscrypto) | Book | Modern primitives and their pitfalls |
| [Cryptopals](https://cryptopals.com/) | Challenges | Break real crypto mistakes |
| [CryptoHack](https://cryptohack.org/) | Platform | Structured crypto challenges |

- [ ] Cryptopals sets 1 and 2
- [ ] CryptoHack: introduction, general, and symmetric tracks
- [ ] Implement AES-CBC and a padding oracle attack against your own server

**Deliverables**
- [ ] `src/crypto_lab/` with typed, tested implementations
- [ ] `docs/crypto_misuse.md` listing 10 common misuse patterns

## Phase 4: Binary Exploitation & Reverse Engineering

Goal: Understand memory corruption and read compiled code.

| Resource | Type | Why |
|----------|------|-----|
| [Hacking: The Art of Exploitation](https://nostarch.com/hacking2.htm) | Book | C, assembly, and exploitation basics |
| [pwn.college](https://pwn.college/) | Platform | Module-based exploitation practice |
| [Practical Malware Analysis](https://nostarch.com/malware) | Book | Static and dynamic analysis |
| [Ghidra](https://ghidra-sre.org/) | Tool | Free disassembler and decompiler |

- [ ] Stack buffer overflows and mitigations (canaries, ASLR, NX)
- [ ] Reverse five small crackme binaries in Ghidra
- [ ] Complete the first pwn.college modules

**Deliverables**
- [ ] `writeups/pwn/` with exploits and explanations

## Phase 5: Offense Practice

Goal: Chain skills across full machines and competitions.

| Resource | Type | Why |
|----------|------|-----|
| [TryHackMe](https://tryhackme.com/) | Platform | Guided learning paths |
| [Hack The Box](https://www.hackthebox.com/) | Platform | Realistic machines |
| [picoCTF](https://picoctf.org/) | CTF | Beginner-friendly annual competition |

- [ ] Finish a TryHackMe beginner path
- [ ] Root 10 retired Hack The Box machines
- [ ] Play 3 live CTFs

**Deliverables**
- [ ] 10 full writeups in `writeups/`

## Phase 6: Defense & Detection

Goal: Detect and respond to the attacks you learned to perform.

| Resource | Type | Why |
|----------|------|-----|
| [Blue Team Labs Online](https://blueteamlabs.online/) | Platform | Investigations and incident response |
| [LetsDefend](https://letsdefend.io/) | Platform | SOC analyst practice |
| [Sigma rules](https://github.com/SigmaHQ/sigma) | Repo | Vendor-neutral detection rule format |
| [Wazuh Documentation](https://documentation.wazuh.com/current/index.html) | Docs | Open-source SIEM and endpoint monitoring |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Framework | How organizations structure security |

- [ ] Deploy Wazuh and ingest logs from a lab target
- [ ] Attack your lab target, then write detections for each step
- [ ] Map detections to MITRE ATT&CK techniques

**Deliverables**
- [ ] `detections/` with 10 tested Sigma rules
- [ ] `docs/incident_report.md` for one simulated attack

## Capstone Projects

- [ ] Home lab: attacker VM, vulnerable target, and a Wazuh server on an isolated virtual network
- [ ] Python port scanner and log analyzer in `tools/`, typed and tested
- [ ] Full attack-and-detect writeup: exploit a target, then show the telemetry and the rule that catches it
- [ ] Publish five sanitized CTF writeups

## Repository Layout

```
cybersecurity/
├── README.md
├── pyproject.toml
├── .pre-commit-config.yaml   # includes secret scanning
├── labs/
│   ├── vuln_app/
│   └── network/              # lab topology and VM setup notes
├── tools/                    # your scanners and analyzers
├── detections/               # Sigma rules and tests
├── writeups/
│   ├── pwn/
│   └── web/
├── tests/
└── docs/
    ├── threat_model_template.md
    ├── crypto_misuse.md
    └── incident_report.md
```

## Engineering Rules

These are strict. A phase is not complete until its deliverables follow all of them.

### 1. Daily 1:3 Theory-to-Building Ratio

- [ ] For every 1 hour of reading or watching, spend 3 hours building, solving, or running labs
- [ ] Log hours in `docs/log.md` at the end of each session
- [ ] No new chapter until the previous one has working code or a written lab report

### 2. Git Branch Hygiene

- [ ] `main` is always green and never receives direct commits
- [ ] One branch per deliverable: `phase-N/short-description`
- [ ] Small commits with imperative messages; squash-merge via PR after checks pass
- [ ] Delete branches after merge

### 3. Quality Gates

- [ ] `mypy --strict` and `pytest` pass on everything in `tools/` and `src/`
- [ ] `ruff check .` passes
- [ ] [detect-secrets](https://github.com/Yelp/detect-secrets) runs in pre-commit so no credentials or flags reach the repo

### 4. Branch-Specific Rules

- [ ] Test only systems you own or have explicit written permission to test, plus platforms built for practice (TryHackMe, Hack The Box, CTFs)
- [ ] Never run scans or exploits against third-party infrastructure, school networks, or neighbors
- [ ] Run vulnerable machines on an isolated virtual network, never bridged to your home LAN
- [ ] Practice responsible disclosure: report bugs privately and give vendors time to fix
- [ ] Do not publish working exploits for unpatched, live systems

## Exit Criteria

- [ ] Exploit and then patch each OWASP Top 10 class in your own lab
- [ ] Explain why a given crypto construction is broken and demonstrate the attack
- [ ] Root a medium Hack The Box machine without a walkthrough
- [ ] Write a detection rule for an attack you performed yourself
