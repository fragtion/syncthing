If you are looking for the original/unmodified Syncthing utility instead, then please go to https://github.com/syncthing/syncthing

## Why the fork?

This is a modified version of Syncthing, designed to function solely as backend synchronizer for Maildirs. If the Maildirs are also being actively accessed by an (IMAP-enabled) mailserver, then additional changes should also made to the mailserver as well (for example: in order to help avoid duplicates, the 'new' folder should be symlinked to its respective 'cur' folder for all Maildir folders, and the mailserver's Maildir libraries should be modified to ignore 'new' altogether - the symlink is retained for MTA delivery purposes.)

The aim of this project is to create a near-synchronous "multi-master", round-robin dovecot cluster without needing to use dovecot's built in replication (which is less bandwidth efficient, and limited to two nodes) or director functions, or the more cumbersome synchronization softwares such as offlineimap, syncmaildir, etc. Syncthing is used to ensure that the underlying maildir content, including any UUID index records, can be synchronized in near-realtime, avoiding the latency bottlenecks of a NAS/NFS-based storage scheme which usually impacts the user's IMAP experience.

WARNING: This probably breaks RFC/spec, and might not scale so well! It works great for me... but YMMV - proceed at own risk.

### Donate
Did this make you happy? I'd love to do more development like this! Please donate to show your support :)

BTC: 1Q4QkBn2Rx4hxFBgHEwRJXYHJjtfusnYfy
XMR: 4AfeGxGR4JqDxwVGWPTZHtX5QnQ3dTzwzMWLBFvysa6FTpTbz8Juqs25XuysVfowQoSYGdMESqnvrEQ969nR9Q7mEgpA5Zm
