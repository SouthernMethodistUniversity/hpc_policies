# Storage Policies

## Overview of Storage

1. Home:
  - Technical Details:
    - 20TB usable
    - Several fundamental directories
      - /cm
      - /hpc
      - /users
  - Restrictions:
    - 200GB quota for all users of /users
2. Scratch:
  - Technical Details:
    - 2.4PB usable
    - Two fundamental directories
      - /scratch/users
      - /scratch/group
  - Restrictions:
    - No quotas for all users
  - Proposed Restrictions and New Usage:
    - Hard 60 day retention
    - No quotas
    - Scratch allocations are given on a per job basis
      - $SCRATCH -> /scratch/jobs/$SLURM_JOB_ID
      - Workflow: $HOME/$WORK -> $SCRATCH -> $HOME/$WORK, $SCRATCH removed
    - Automatic email notification one week prior to deletion
    - /scratch/group usage remains as is
3. NFS Scratch:
   - Technical Details:
     - 3TB usable
   - Restrictions:
     - Restricted to specific users
     - No quotas for authorized users
4. Work:
  - Technical Details:
    - ~800TB usable
    - High inodes to allow for many files
  - Proposed Restrictions:
    - 8TB per person, no time limit

## Proposed Timeline for New $WORK and $SCRATCH Policies

August 14
- M2 backup after maintenance
- $WORK available for testing

August 15
- Begin new workflow testing

August 17
- Documentation and education materials are available
- Video dicussing implemention, etc. available
- Communication with users of migration plan and policy changes
- Encourage users to being cleaning their /scratch/users directory
- Encourage users to use groups for shared and/or ephemeral data (such as ATLAS data)

September 1
- Work becomes available
- New $SCRATCH pointing to job-specifc directory is available
- Users begin migrating data from /scratch/users to $WORK (cleaning up as they go)

December 1
- Make /scratch/users read only

December 31
- Remove $HOME/scratch symlinks that point to /scratch/users/$USER
- Remove /scratch/users

