# Backup & Disaster Recovery Plan

## Backup Strategy

- Daily encrypted backups to AWS S3 (versioned & encrypted)
- Weekly full backup to offline NAS (Synology NAS)

## Recovery Objectives

- Recovery Time Objective (RTO): 4 hours
- Recovery Point Objective (RPO): 1 day

## Backup Testing

- Monthly test restore of AWS S3 backup
- Quarterly full disaster recovery drill using NAS backups

## Disaster Recovery Scenarios

1. Ransomware attack:
    - Isolate infected systems
    - Restore from clean AWS backup
    - Forensic investigation & root cause analysis

2. Hardware failure:
    - Replace failed hardware
    - Restore from AWS or NAS backup

3. Natural disaster (fire, flood, etc.):
    - Relocate to secondary site / cloud-hosted environment
    - Restore from AWS S3 backup