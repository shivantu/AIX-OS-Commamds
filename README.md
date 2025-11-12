```bash
╔══════════════════════════════════════════════════════════════════════════════╗
║                         🚀 AIX 7.3 COMPLETE COMMAND REFERENCE               ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║  🔥 STORAGE & LVM MANAGEMENT                                                 ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  lspv | lsvg | lslv                    # List physical/logical volumes      ║
║  mkvg -y datavg hdisk1                 # Create volume group                ║
║  extendvg rootvg hdisk2                # Add disk to volume group           ║
║  mklv -y mylv datavg 10G               # Create 10GB logical volume         ║
║  extendlv mylv 5G | chfs -a size=+5G   # Increase LV & filesystem size      ║
║  rmlv mylv | reducevg myvg hdisk1      # Remove LV & disk from VG           ║
║                                                                              ║
║  💾 FILE SYSTEM OPERATIONS                                                   ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  df -m | du -sm /home                  # Check disk usage                   ║
║  lsfs | mount /myfs | umount /myfs     # List/mount/unmount filesystems     ║
║  crfs -v jfs2 -g datavg -m /data -a size=20G  # Create 20GB filesystem      ║
║  rmfs -r /oldfs                        # Remove filesystem                  ║
║                                                                              ║
║  🧠 MEMORY & CPU MANAGEMENT                                                  ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  svmon -G                              # Memory statistics                  ║
║  lsps -a | mkps -s 50 rootvg           # List/create paging space           ║
║  chps -s 10 hd6                        # Increase paging space              ║
║  lparstat -i | pmcycles -m             # CPU/LPAR details & frequencies     ║
║  ps -eo pid,ppid,pcpu,pmem,comm        # Processes with CPU/memory usage    ║
║                                                                              ║
║  👥 USER & GROUP MANAGEMENT                                                  ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  mkuser john | rmuser -p john          # Create/remove user                 ║
║  lsuser john | chuser maxage=8 john    # List/modify user attributes        ║
║  passwd john                           # Change user password               ║
║  mkgroup dba | rmgroup dba             # Create/remove group                ║
║  lsgroup staff | chgroup users john    # List groups / add user to group    ║
║  lsuser -a groups john                 # Show user's group memberships      ║
║                                                                              ║
║  🔐 PERMISSIONS & OWNERSHIP                                                 ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  chmod 755 script.sh                   # rwxr-xr-x permissions              ║
║  chmod u+x file | chmod g-w file       # Add/remove permissions             ║
║  chown oracle:dba file.txt             # Change owner & group               ║
║  chgrp apps /data                      # Change group ownership             ║
║  aclget file | aclput acl.file         # Get/set ACLs                       ║
║                                                                              ║
║  ⚡ PROCESS MANAGEMENT                                                       ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  ps -ef | grep java                    # Find specific processes            ║
║  kill -9 1234 | killall java           # Kill process by PID/name           ║
║  renice -n 5 -p 5678                   # Change process priority            ║
║  nohup ./start.sh &                    # Run process immune to hangups      ║
║  topas                                 # Interactive system monitor         ║
║                                                                              ║
║  🌐 NETWORK CONFIGURATION                                                   ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  ifconfig -a                           # Show all network interfaces        ║
║  entstat -d ent0 | netstat -rn         # Interface stats & routing table    ║
║  mktcpip -h server1 -a 192.168.1.10 -m 255.255.255.0 -i en0  # Configure IP ║
║  host $(hostname) | ping 8.8.8.8       # DNS lookup & connectivity test     ║
║                                                                              ║
║  🔧 SYSTEM INFO & DIAGNOSTICS                                               ║
║  ──────────────────────────────────────────────────────────────────────────  ║
║  oslevel -s                            # Show AIX TL/SP version             ║
║  prtconf | lscfg -vp                   # Hardware configuration & details   ║
║  errpt -a | errclear 0                 # View/clear error logs              ║
║  bootlist -m normal hdisk0             # Set boot device                    ║
║  diag                                  # Run hardware diagnostics           ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```
