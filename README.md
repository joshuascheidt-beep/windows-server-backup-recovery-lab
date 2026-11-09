# Windows Server Backup and Recovery Lab

A backup job can finish successfully and still leave one question unanswered: can you recover what you need?

In this AMU lab, I configured Windows file sharing and Distributed File System (DFS) across two lab servers, set up a scheduled backup with Windows Server Backup, and used Robocopy to copy files between servers. I checked the destination folders on both servers to see what was actually there.

## What I did

| Task | What I checked |
| --- | --- |
| Configured Windows shares and DFS | The shares appeared on both servers, and the namespace was visible in DFS Management. |
| Configured Windows Server Backup | I checked the schedule summary and inspected the backup folders on both servers. |
| Created and ran a Robocopy script | I inspected the destination folders on both servers after the copy. |
| Compared Robocopy with XCOPY | I documented an XCOPY alternative and explained why I would keep Robocopy for a workflow that needs more control over logging and mirroring. |

## What the lab proved

The destination checks showed that files were present. They didn't establish whether I could recover an earlier version after an accidental deletion or verify that restored permissions were correct. A mirror can carry unwanted changes to the destination, so I would keep a separate versioned backup for recovery.

## What I'd test next

1. Save the hash and permissions of a test file before backing it up.
2. Change or delete the file, then restore the earlier version to a separate folder.
3. Compare the restored hash and permissions with the originals. Record the recovery time and any steps that needed manual work.

**Tools:** Windows Server Backup, DFS Management, Windows file shares, Robocopy, and XCOPY.

