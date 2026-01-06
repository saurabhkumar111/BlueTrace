# BlueTrace – Phase 1: Lab Setup & Baseline

## Objective
Prepare a clean and reproducible lab environment for SSH brute-force detection.

## Lab Components
- Attacker: Kali Linux
- Victim: Ubuntu Server
- Service: OpenSSH

## Verification Performed
- SSH service running and reachable
- Password-based authentication enabled
- Weak demo user (sshuser) created
- Manual failed and successful SSH logins observed
- Authentication logs verified in /var/log/auth.log

## Evidence Collected
- Baseline authentication log captured before attack
- File: auth.log.baseline
- Integrity preserved using SHA256 hash

## Status
Phase-1 completed successfully. Environment ready for attack simulation (Phase-2).

