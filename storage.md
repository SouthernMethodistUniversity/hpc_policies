# Storage Policies

## Overview of Storage

1. Home: 20TB usable, 200GB quota for all users
2. Scratch: 2.4PB usable, no quotas for all users
  - New policy:
    - 60 day retention (hard with email)
    - /scratch/jobs/<job_id> -> $SCRATCH
      export SCRATCH=/scratch/jobs/<job_id>
      mkdir $SCRATCH
      chown user:user $SCRATCH
      chmod g-rwx $SCRATCH
      - Educate users on new work/home -> scratch -> work/home workflow and cleaning up scratch
    - Migration plan with timeline to move stuff off scratch to work
      - End of the year to move to work
      - December make /scratch/users read only
      - Remove /scratch/users
      - Sometime before end of year remove scratch symlinks
      - Leave /scratch/group as is and continue to use it
3. NFS Scratch: 3TB usable, restricted to specific users, no quotas for these users
4. Work: ~800TB usable
  - Quotas
    - 8TB per person, no time limit
  - High inodes to allow for many files

## Timeline

August 14
- M2 backup after maintenance

August 15
- New workflow testing

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
