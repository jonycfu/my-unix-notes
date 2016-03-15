# my-unix-notes
Personal notes on UNIX Commands

`$` denotes the command line carriage

##Variables 

Any Single-session variables can be created on the terminal:

  `$ any_variable_you_want=random_value`

To reference the value of those variables, use `$` prefix:

  `$ echo $any_variable_you_defined #outputs random_value`

To find your system variables, which persist in terminal:

  `$ env`

One system variable that comes up often is the `PATH`. What is it?

  `$ echo $PATH`
  `/home/jonfu/.nvm/versions/node/v5.8.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games`

  Basically, it is a list of directories to search for executables (Notice the `../bin/` directories referenced)

Typically, if you want custom variables to be initialized on startup:

  ~/.profile
  ~/.bashrc
  ~/.zshrc

##Command History

Ever want to see a list of commands you've ever executed `( x < 10000 )`?

  `$ history`

##User Management

Add user
  `$ sudo adduser user_name`

Change user password:

  `$ sudo passwd user_name`

Check users list

  `$ users`

For logged-in users, including their IP address

  `$ who`

To substitute user, for session

  `$ su`

To Realtime chat with other users (as long as `mesg` receptor is turned ON)

  `$ write user_name`

For message to ALL users

  `$ wall`

##Virtual Consoles

VCs are useful for testing...it is a text-only interfacing environment
by default, linux comes in six 'tty[n]' VCs,
where 'n' is mapped to your `F1` to `F6` Function Keys.

To enter a VC, use:

  `<Ctrl-Alt-[F[n]]>`

To return to GUI Console:

  `<Ctrl-Alt-F7>`

##File Directory Hierarchy

`/root` -- Root-only Directory (Root Home)

`/bin` -- Binaries

`/sbin` -- System Admin Binaries

`/boot` -- Startup Boot Files (`vmlinuz` is the linux kernal)

`/dev` -- Devices

`/usr` -- User Programs (default installation binaries go here)

`/etc` -- Service Configurations

`/lib` -- Libraries with reusable linux source code

`/media` -- Mounted mediums (e.g. USB, CD-ROM)

`/proc` -- Current Hardware-related Information (Not stored on hard drive)

`/sys` -- Stored Hardware-related Information (Stored on hard drive)

`/var` -- Record logs, events, jobs, ...etc

##File Directory Operations

To find disk usage

  `$ sudo du -hs /directory_name`

To find system info
  `$ uname`

To word count
  `$ wc file_name`

To use wildcard in file queries

  `$ ls *.js`
  `$ ls *some_suffix.*`

Remember that copy `cp` does not copy hidden files by default

##Understanding File Attributes

Assume I ran `$ ls -l /home`, with the following isolated output

  ```
  drwxr-xr-x   3 jonfu vboxusers 4.0K Jan 23 11:48 .vim
  -rw-------   1 jonfu vboxusers  38K Mar 15 14:35 .viminfo
  -rw-------   1 jonfu vboxusers    0 Jan 30 23:43 .viminfo.tmp
  -rw-r--r--   1 jonfu vboxusers  20K Mar 15 16:30 .vim_mru_files
  -rw-r--r--   1 jonfu vboxusers  479 Jan 29 14:35 .vimrc
  drwxr-xr-x   8 jonfu vboxusers 4.0K Jan 30 23:12 .vim_runtime
  ```
  
  File Type | Permissions(9) | Ownership | File Size | Date Created | File Name
  --- | --- | --- | --- | --- | ---
  `d` | `rwxr-xr-x` | `jonfu vboxusers` | `4.0K` | `Jan 23 11:48` | `.vim`

