# 1.Cat:not the pet, but command!
read a file present in the home directory with cat command to obtain flag.

## MY SOLVE
**FLAG:** `pwn.college{gpZTsezPTBbI2D6Uifej_hCxj9o.QXxcTN0wSNxkjNzEzW}`

clearly mentioned flag has been copied to the flag file. So open the the flag file using `cat flag`(present in home directory so need for path).
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{gpZTsezPTBbI2D6Uifej_hCxj9o.QXxcTN0wSNxkjNzEzW}
```

## WHAT I LEARNED 
the use of `cat` command is for reading out files. Cat will concatenate multiple files if provided multiple arguments. `cat file1 file2 ` reads both the contents of file1 and file2.

## REFERENCES 
none.


# 2.Catting absolute paths
reading a file that is not present in the home directory.

## MY SOLVE
**flag:** `pwn.college{k3bhKPKxUMhVEMfuYWS5qavkAG3.QX5ETO0wSNxkjNzEzW}`
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{k3bhKPKxUMhVEMfuYWS5qavkAG3.QX5ETO0wSNxkjNzEzW}
```
since its not in the main directory, to read the the file we can use its absolute path with the command `cat /flag`.

## WHAT I LEARNED 
using `cat` command to read a file not present in the main directory.

## REFERENCES 
none.


# 3.MORE CATTING PRACTICE
reading a file with its absolute path present in a random directory.

## MY SOLVE
**FLAG:** `pwn.college{srSvxZiDYDxAap8BUQgtgtoPFW0.QXwITO0wSNxkjNzEzW}`
```
hacker@commands~more-catting-practice:~$ cat /usr/lib/dbus-1.0/flag
pwn.college{srSvxZiDYDxAap8BUQgtgtoPFW0.QXwITO0wSNxkjNzEzW}
```
the absolute path of the flag was clearly mentioned. Simply plugged in the absolute path as argument to the `cat` command.

## WHAT I LEARNED 
using `cat` to read a file with its absolute path.

## REFERENCES 
none.


# 4.GREPPING FOR A NEEDLE IN A HAYSTACK
use grep command to search for the flag

## MY SOLVE 
**FLAG:** `pwn.college{00F8sgBvBxNmCz1b6dryVDRasDV.QX3EDO0wSNxkjNzEzW}`
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{00F8sgBvBxNmCz1b6dryVDRasDV.QX3EDO0wSNxkjNzEzW}

```
used the grep command with the mentioned text and path of the file as argument.

## WHAT I LEARNED 
sometimes, files are too big for cat command, so `grep` is used to search for the contents of the file. grep will search the file for lines of text containing the given string to search and print them to the console.

## REFERENCES 
none.


# 5.COMPARING FILES 
use `diff` command to find the difference between two files to obtain flag.

## MY SOLVE 
**FLAG:**  `pwn.college{ksQTH0hBhaHsIeN1j7BZjORFOKH.01MwMDOxwSNxkjNzEzW}`
```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
4a5
> pwn.college{ksQTH0hBhaHsIeN1j7BZjORFOKH.01MwMDOxwSNxkjNzEzW}
```
used the `diff` command to compare the two given files line by line and find the difference to get the flag. First file contains 100 fake flags, second contains 100 fake and one real flag. Simply the different line is printed.

## WHAT I LEARNED 
finding similiarities by eye balling two files is hard and not feasible, the command `diff` is used to compare the files line by line. The command exactly tells us the difference and prints it. `XcX` tells us that theres a difference in the X line of first and second file. `XaY` tells us that after line X of first file, line Y was added in second file, the difference being the Y line.

## REFERENCES 
none.

# 6.LISTING FILES 
list the contents of a directory to find the file containing flag

## MY SOLVE 
**FLAG:** `pwn.college{4QtxmUjtudQoIbUYSwiIfjW431i.QX4IDO0wSNxkjNzEzW}`
```
hacker@commands~listing-files:~$ ls /challenge
28390-renamed-run-27175  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/28390-renamed-run-27175
Yahaha, you found me! Here is your flag:
pwn.college{4QtxmUjtudQoIbUYSwiIfjW431i.QX4IDO0wSNxkjNzEzW}
```
used `ls` to list down the files in the `challenge` directory.File was given, simply opened the file to get the flag.

## WHAT I LEARNED 
the `ls` command is used to list down the files/directories inside a directory.

## REFERENCES 
none.


# 7.TOUCHING FILES 
create file using `touch` command.

## MY SOLVE 
**FLAG:** `pwn.college{0t87AIUyMfbRyhkIVsgRgyAVcJ2.QXwMDO0wSNxkjNzEzW}`
```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{0t87AIUyMfbRyhkIVsgRgyAVcJ2.QXwMDO0wSNxkjNzEzW}
```
used the `touch` command to create two files in the home directory and ran `/challenge/run` to get flag.

## WHAT I LEARNED 
`touch` command used to create files.

## REFERENCES 
none.

# 8. REMOVING FILES 
remove a file from directory using `rm` command.

## MY SOLVE 
**FLAG:** `pwn.college{YMr6loxLCyPE_dBcX_pbTgusEU-.QX2kDM1wSNxkjNzEzW}`
```
hacker@commands~removing-files:~$ ls
Desktop  delete_me  f
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
Desktop  f
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{YMr6loxLCyPE_dBcX_pbTgusEU-.QX2kDM1wSNxkjNzEzW}
```
listed the files to be deleted using `ls` and used `rm` to delete the files to obtain the flag.

## WHAT I LEARNED 
`rm` command used to delete files.

## REFERENCES 
none.


# 9. MOVING FILES 
use the `mv` command to move files to obtain flag.

## MY SOLVE 
**FLAG:** `pwn.college{EH71C3CU3t22YgoqDAfDpOWv_8b.0VOxEzNxwSNxkjNzEzW}`
```
hacker@commands~moving-files:~$ ls
Desktop  f
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/hack
bash: /challenge/hack: No such file or directory
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{EH71C3CU3t22YgoqDAfDpOWv_8b.0VOxEzNxwSNxkjNzEzW}
```
used the `mv` command to move the file `/flag` into `/tmp/hack-the-planet`. Then ran /challenge/check to obtain flag.

## WHAT I LEARNED
used the `mv` command to move one file into another.

## REFERENCES 
none.


# 10. HIDDEN FILES
find the hidden files using `ls -a` command.

## MY SOLVE 
**flag:** `pwn.college{Qzwwx1rwLyOI9ZFFV4VCSlmuh9N.QXwUDO0wSNxkjNzEzW}`
```
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv             bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-285592085010674  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat /.flag-285592085010674
pwn.college{Qzwwx1rwLyOI9ZFFV4VCSlmuh9N.QXwUDO0wSNxkjNzEzW}
```
switched from home directory to the mentioned `/` category. Used `ls -a` to list all the files including hidden files. Used `cat` to read contents of the hidden file.

## WHAT I LEARNED 
by default linux does not show the list of the files that start with `.`. Hence we use a modified command of list that is `ls -a` to be able to view all the possible files in the directory.

## REFERENCES 
none.


# 11. AN EPIC FILESYSTEM QUEST
find the flag using learned commands. 

## MY SOLVE 
**FLAG:** `pwn.college{I2sfbBs-vFiqhD5EsBdB2F1X4h1.QX5IDO0wSNxkjNzEzW}`
```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.  ..  .dockerenv  MESSAGE  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat MESSAGE
Lucky listing!
The next clue is in: /opt/kropr/target/release/.fingerprint/unicode-ident-1cf4f389b3b3ef11

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/kropr/target/release/.fingerprint/unicode-ident-1cf4f389b3b3ef11
hacker@commands~an-epic-filesystem-quest:/opt/kropr/target/release/.fingerprint/unicode-ident-1cf4f389b3b3ef11$ ls -a
.  ..  .GIST  dep-lib-unicode_ident  invoked.timestamp  lib-unicode_ident  lib-unicode_ident.json
hacker@commands~an-epic-filesystem-quest:/opt/kropr/target/release/.fingerprint/unicode-ident-1cf4f389b3b3ef11$ cat .GIST
Congratulations, you found the clue!
The next clue is in: /usr/share/locale/nl

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/kropr/target/release/.fingerprint/unicode-ident-1cf4f389b3b3ef11$ cd /usr/share/locale/nl
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/nl$ ls -a
.  ..  LC_MESSAGES  MEMO
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/nl$ cat MEMO
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/arch/parisc/kernel/syscalls
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/nl$ cat LC_MESSAGES
cat: LC_MESSAGES: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/nl$ cd  /opt/linux/linux-5.4/arch/parisc/kernel/syscalls
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/parisc/kernel/syscalls$ ls -a
.  ..  Makefile  SECRET  syscall.tbl  syscallhdr.sh  syscalltbl.sh
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/parisc/kernel/syscalls$ cat SECRET
Yahaha, you found me!
The next clue is in: /usr/share/perl/5.30.0/CPAN/FTP

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/parisc/kernel/syscalls$ cd /usr/share/perl/5.30.0/CPAN/FTP
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ ls -a
.  ..  EVIDENCE  netrc.pm
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ cat EVIDENCE
Congratulations, you found the clue!
The next clue is in: /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$  /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe/.
bash: /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe/.: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ ls /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe
CLUE-TRAPPED  xgbe-common.h  xgbe-debugfs.c  xgbe-dev.c  xgbe-ethtool.c  xgbe-main.c  xgbe-pci.c     xgbe-phy-v2.c    xgbe-ptp.c
Makefile      xgbe-dcb.c     xgbe-desc.c     xgbe-drv.c  xgbe-i2c.c      xgbe-mdio.c  xgbe-phy-v1.c  xgbe-platform.c  xgbe.h
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ cat CLUE-TRAPPED
cat: CLUE-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ touch CLUE-TRAPPED
touch: cannot touch 'CLUE-TRAPPED': Permission denied
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ cat Makefile
cat: Makefile: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ ls -a  /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe
.   CLUE-TRAPPED  xgbe-common.h  xgbe-debugfs.c  xgbe-dev.c  xgbe-ethtool.c  xgbe-main.c  xgbe-pci.c     xgbe-phy-v2.c    xgbe-ptp.c
..  Makefile      xgbe-dcb.c     xgbe-desc.c     xgbe-drv.c  xgbe-i2c.c      xgbe-mdio.c  xgbe-phy-v1.c  xgbe-platform.c  xgbe.h
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ cat /opt/linux/linux-5.4/drivers/net/ethernet/amd/xgbe/CLUE-TRAPPED
Tubular find!
The next clue is in: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/term
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/CPAN/FTP$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/term
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/term$ ls -a
.   WHISPER      __pycache__   key.py        keymap.py    spinners.py  termcap.py  unix_termcap.py
..  __init__.py  completer.py  keyconsts.py  readline.py  term.py      text.py     windows_termcap.py
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/term$ cat WHISPER
Tubular find!
The next clue is in: /opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/term$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__$ ls -a
.                             ber.cpython-38.pyc            ed25519key.cpython-38.pyc      kex_gss.cpython-38.pyc  sftp.cpython-38.pyc           transport.cpython-38.pyc
..                            buffered_pipe.cpython-38.pyc  file.cpython-38.pyc            message.cpython-38.pyc  sftp_attr.cpython-38.pyc      util.cpython-38.pyc
.NUGGET                       channel.cpython-38.pyc        hostkeys.cpython-38.pyc        packet.cpython-38.pyc   sftp_client.cpython-38.pyc    win_openssh.cpython-38.pyc
__init__.cpython-38.pyc       client.cpython-38.pyc         kex_curve25519.cpython-38.pyc  pipe.cpython-38.pyc     sftp_file.cpython-38.pyc      win_pageant.cpython-38.pyc
_version.cpython-38.pyc       common.cpython-38.pyc         kex_ecdh_nist.cpython-38.pyc   pkey.cpython-38.pyc     sftp_handle.cpython-38.pyc
_winapi.cpython-38.pyc        compress.cpython-38.pyc       kex_gex.cpython-38.pyc         primes.cpython-38.pyc   sftp_server.cpython-38.pyc
agent.cpython-38.pyc          config.cpython-38.pyc         kex_group1.cpython-38.pyc      proxy.cpython-38.pyc    sftp_si.cpython-38.pyc
auth_handler.cpython-38.pyc   dsskey.cpython-38.pyc         kex_group14.cpython-38.pyc     rsakey.cpython-38.pyc   ssh_exception.cpython-38.pyc
auth_strategy.cpython-38.pyc  ecdsakey.cpython-38.pyc       kex_group16.cpython-38.pyc     server.cpython-38.pyc   ssh_gss.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__$ cat .NUGGET
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/arch/ia64/include/asm

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__$ ls /opt/linux/linux-5.4/arch/ia64/include/asm
CUE-TRAPPED       bug.h          div64.h              fpswa.h        iosapic.h         local.h        native      pgtable.h    spinlock_types.h  unaligned.h
Kbuild            bugs.h         dma-mapping.h        ftrace.h       irq.h             local64.h      nodedata.h  processor.h  string.h          uncached.h
acenv.h           cache.h        dma.h                futex.h        irq_regs.h        mca.h          numa.h      ptrace.h     switch_to.h       unistd.h
acpi-ext.h        cacheflush.h   dmi.h                gcc_intrin.h   irq_remapping.h   mca_asm.h      page.h      sal.h        syscall.h         unwind.h
acpi.h            checksum.h     early_ioremap.h      hardirq.h      irqflags.h        meminit.h      pal.h       sections.h   termios.h         user.h
agp.h             clocksource.h  elf.h                hugetlb.h      kdebug.h          mman.h         param.h     serial.h     thread_info.h     ustack.h
asm-offsets.h     cpu.h          emergency-restart.h  hw_irq.h       kexec.h           mmiowb.h       parport.h   shmparam.h   timex.h           uv
asm-prototypes.h  cputime.h      esi.h                idle.h         kmap_types.h      mmu.h          patch.h     signal.h     tlb.h             vga.h
asmmacro.h        current.h      exception.h          intrinsics.h   kprobes.h         mmu_context.h  pci.h       smp.h        tlbflush.h        xor.h
atomic.h          cyclone.h      export.h             io.h           kregs.h           mmzone.h       percpu.h    sn           topology.h
barrier.h         delay.h        extable.h            iommu.h        libata-portmap.h  module.h       perfmon.h   sparsemem.h  types.h
bitops.h          device.h       fb.h                 iommu_table.h  linkage.h         msidef.h       pgalloc.h   spinlock.h   uaccess.h
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/paramiko/__pycache__$ cat /opt/linux/linux-5.4/arch/ia64/include/asm/CUE-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{I2sfbBs-vFiqhD5EsBdB2F1X4h1.QX5IDO0wSNxkjNzEzW}
```
started simple, switched to given `/` directory and listed files. Next steps were a series of switching to different directories and listing out hidden files and then reading the files which were hinted. Also used absolute paths to read out files instead of swicthing to the directory. Honestly, just followed the steps and hints provided.

## WHAT I LEARNED 
the use of `ls -a` `cat` `cd` commands properly. Fun hunt!

## REFERENCES 
none.

# 11. MAKING DIRECTORIES
create a directory and a file to obtain the flag.

## MY SOLVE 
**FLAG:** `pwn.college{AJ0JT3tcVobSU72z2zhs-pSWGXx.QXxMDO0wSNxkjNzEzW}`
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{AJ0JT3tcVobSU72z2zhs-pSWGXx.QXxMDO0wSNxkjNzEzW}
```
simply created a new directory using `mkdir` and changed to it. Created a new file using `touch` command. 

## WHAT I LEARNED 
`mkdir` is used to make a directory.


# 13. LINKING FILES 
create a symbolic link to read out the flag.

## MY SOLVE 

**FLAG:** `pwn.college{0Hr5JWY-Pf7v1OMPuu7wCIsCr6-.QX5ETN1wSNxkjNzEzW}`
```
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{0Hr5JWY-Pf7v1OMPuu7wCIsCr6-.QX5ETN1wSNxkjNzEzW}
```
set a symbolic link using the `ln -s ` command between the original flag file and the duplicate file. Since the command would read the contents of the address of the duplicate file, a symbolic link that lead to the original file works.

## WHAT I LEARNED 
command to create a symbolic link, differences between hard link and soft(symbolic) link.

## REFERENCES 
SYMBOLIC LINKS VIDEO in pwn.college








