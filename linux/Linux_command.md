# Linux command

- ls, cd, pgrep, pkill, kill, vim
- echo, chown, chmod, grep
- tar, unzip, screen, tmux, atop, df, du
- curl, wget, clear, history
- rsync, scp, rm, cp, mv, ssh, touch
- cat, zcat, tac, tail, head, cut, sort, uniq, wc

## ls

`List directory contents.`

__Ex__:

```bash
ls
ls -a
ls -l
```

## cd

`Change the working.`

__Ex__:

```bash
cd Desktop/
```

## pgrep, pkill

`Look  up  or signal processes based on name and other attributes.`

> SYNOPSIS:
> - pgrep [options] pattern
> - pkill [options] pattern

__Description__:
Pgrep looks through the currently running processes and lists the process IDs
which matches the selection criteria to stdout. All the criteria have to match.

Pkill will send the specified signal (by default SIGTERM) to each process
instead of listing them on standard output.

__Ex__:

Find process ID of the named process.

```bash
pgrep -u root named
```

Send the HUP signal to syslogd, which forces it to re-read its configuration file.

```bash
pkill -HUP syslogd
```

## kill

`Kill is used to send a signal to a process.`

> SYNOPSIS:
> - kill [-s] [-l] %pid

__Description__:
The default signal for kill is TERM (which will terminate or "kill" the process).
Use -l or -L to list available signals.

__Ex__:

Kills all processes possible to be killed.

```bash
kill -9 -1
```

Sends the default signal (TERM) to the processeswith IDs 123, 543, 2341,
and 3453, terminating those processes.

```bash
kill 123 543 2341 3453
```

## vim

`Editer in command.`

> SYNOPSIS:
> - vi [namefile]

__Description__:
Create and modify file in terminal.

__Ex__:

Create a file:

```bash
vi test.py

vi test.txt
```

Save file after edit:

```bash
:w
```

Exit file:

```bash
:q
```

## echo

`Display a line of text.`

> SYNOPSIS:
> - echo [SHORT-OPTION]... [STRING]...
> - echo LONG-OPTION

__Description__:
It is frequently used in scripts,batch files,
and as part of individual commands; anywhere you may need to insert text.

__Ex__:

Show line text:

```bash
echo "Hello, World!"

echo $x
```

## chown

`The chown command changes the owner and owning group of files.`

> SYNOPSIS:
> - chown [OPTION]... [OWNER][:[GROUP]] FILE...
> - chown [OPTION]... --reference=RFILE FILE...

__Description__:
Chown changes the user or group ownership of each given file.
If only an owner (a user name or numeric user ID) is given,
that user is made the owner of each given file, and the files' group is not changed.

__Ex__:

Set the owner of file file.txt to user khainguyen.

```bash
chown khainguyen file.txt
```

Recursively grant ownership of the directory `/files/work`,
and all files and subdirectories, to user khainguyen.

```bash
chown -R khainguyen /files/work
```

## chmod

`Change the permissions of files or directories.`

> SYNOPSIS:
> - chmod options permissions file name

__Description__:
Chmod is used to change the permissions of files or directories.

__Ex__:

Change permission for myfile.

```bash
chmod u=rwx,g=rx,o=r myfile
```

u: user

g: group

o: owner

OR:

```bash
chmod 754 myfile
```

0: no permission

1: can execute

2: can write

4: can read

## grep

`which stands for "global regular expression print," processes text
line by line and prints any lines which match a specified pattern.`

> SYNOPSIS:
> - grep [OPTIONS] PATTERN [FILE...]

__Ex__:

Find history content `test`

```bash
history | grep "test"
```

Find and count line content `abc`

```bash
grep -c 'abc' tmp.txt
```

## tar

`The tar program is used to create, maintain, modify,and extract files that are
archived in the tar format.`

> SYNOPSIS:
> - tar [-] A --catenate --concatenate | c --create | d --diff
--compare | --delete | r --append | t --list | --test-label | u --update|
x --extract --get [options] [pathname ...]

__Description__:
It is an archiving file format.

__Ex__:

Create archive archive.tar containing files file1 and file2.

```bash
tar -cf archive.tar file1 file2
```

Extract file from archive.tar.gz.

```bash
tar -xzvf archive.tar.gz
```

## unzip

`The unzip command lists, extracts, and tests compressed files in a ZIP archive.`

> SYNOPSIS:
> - unzip [-Z] [-cflptTuvz[abjnoqsCDKLMUVWX$/:^]] file[.zip]
[file(s) ...] [-x xfile(s) ...] [-d exdir]

__Description__:
Unzip will list, test, or extract files from archives of the zip format,
which are most commonly found on MS-DOS and Windows systems.

__Ex__:

Extract the file from tmp.zip

```bash
unzip tmp.zip
```

## tmux

`tmux is a terminal multiplexer. It lets you switch easily between several
programs in one terminal,detach them (they keep running in the background)
and reattach them to a different terminal.And do a lot more.`

## df

`The df command reports the amount of available disk space being used by file systems.`

> SYNOPSIS:
> - df [OPTION]... [FILE]...

__Description__:
df displays the amount of disk space available on the file system
containing each file name argument.

__Ex__:

Display all file systems and their disk usage.

```bash
df
```

Display the amount of free space in the Desktop directory

```bash
df Desktop/
```

## du

`du estimates and displays the disk space used by files.`

> SYNOPSIS:
> - du [OPTION]... [FILE]..
> - du [OPTION]... --files0-from=F

__Ex__:

Display all file extention .txt and disk space use by file.

```bash
du -s `.txt
```

## curl

`curl is a tool to transfer data from or to a server.`

> SYNOPSIS:
> - curl [options] [URL...]

__Description__:
curl is used in command lines or scripts to transfer data.
It is also used in cars, television sets, routers, printers,
audio equipment, mobile phones, tablets, settop boxes,
media players and is the internet transfer backbone for thousands of
software applications affecting billions of humans daily.

__Ex__:

Fetch the file index.htm from www.computerhope.com using the HTTP protocol.

```bash
curl https://www.computerhope.com/index.htm
```

Fetch the same file as above, but redirect the output to a file, index.htm,
in the current directory.

```bash
curl -O https://www.computerhope.com/index.htm
```

## wget

`Download files via HTTP or FTP.`

> SYNOPSIS:
> - wget [option]... [URL]...

__description__:
Wget is a free utility for non-interactive download of files from the web.
It supports HTTP, HTTPS, and FTP protocols, as well as retrieval through HTTP proxies.

__Ex__:

Download file file.zip

```bash
wget http://website.com/files/file.zip
```

## clear

`Clears the screen.`

> SYNOPSIS:
> - clear

## history

`Download files via HTTP or FTP.`

> SYNOPSIS:
> - history [-c] [-d offset ] [ n ]
> - history -anrw [ file name ]
> - history -ps arg [ arg... ]

__Description__:
displays or manipulate the history list with line numbers,
prefixing each modified entry with a '`'.
An argument of n lists only the last b entries.

__Ex__:

Show all history command

```bash
history
```

## scp

`Copy files securely over a network connection.`

> SYNOPSIS:
> - scp [-12346BCpqrv] [-c cipher] [-F ssh_config] [-i identity_file]
[-l limit] [-o ssh_option] [-P port] [-S program] [[user@]host1:]file1 ...
[[user@]host2:]file2

__Description__:
Copy file between host or server user ssh.

__Ex__:

Copy file setup from local to server w1

```bash
scp ~/my_project/setup.sh w1:~/khainguyen
```

## touch

`touch changes file timestamps.`

> SYNOPSIS:
> - touch [OPTION]... FILE...

__Description__:
The touch command updates the access and modification times of each FILE
 to the current system time.

__Ex__:

If file.txt exists, touch updates its access and modification times to
the current time. If file.txt doesn't exist, it is created as a new, empty file.

```bash
touch file.txt
```

## tac

`Concatenate and print files in reverse.`

## tail

`Tail outputs the last part, or "tail", of files.`

## head

`Head makes it easy to output the first part of files.`

## sort

`Sort sorts the contents of a text file, line by line.`

## uniq

`Uniq reports or filters out repeated lines in a file.`

## wc

`Prints a count of newlines, words, and bytes for each input file.`
