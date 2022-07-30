### Restic Backup

**Basic Commands**
```
// initialize
restic init -r <backup-dir>

// backup
restic -r <backup-dir> backup <main-dir>

// backup while excluding files
restic -r <backup-dir> backup <main-dir> --exclude-file=<exclude-txt-file>
restic -r <backup-dir> backup <main-dir> --exclude="*.txt"

// check snapshots
restic -r <backup-dir> snapshots

// restore from snapshot
restic -r <backup-dir> restore <snapshot-id> --target <restore-dir>
```

<br/>

### Example Scenario  
There are 3 folders in the `root` directory.
```
root
 |_ main
 |_ backup
 |_ restored
```
The original files will be stored in `/root/main` directory.  
The backup files will be stored in `/root/backup` directory.  
The restored file from `/root/backup` directory will be stored in `/root/restored` directory.

<br/>

**Initialize Repository**  
To prepare disk for creating backups for the first time, run this:

```
restic init -r root/backup/
```

<br/>

**Backup Files**  
To backup all the data from `/root/main` to `/root/backup`, run this:
```
restic -r root/backup/ backup root/main/
```

<br/>

**Restore Backup**  
To find the snapshot in `/root/backup` that you're trying to restore, run this:
```
restic -r root/backup/ snapshots
```
To restore data from `/root/backup` to `/root/restored` using the snapshot, run this:
```
restic -r root/backup/ restore <snapshot-id> --target root/restored/
```

<br/>

More Information: https://restic.net/