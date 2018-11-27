<img src="assets/bash-full.png" style="border: none; background: none;">

---

## History

#### [In the Beginning was the Command Line](http://cristal.inria.fr/~weis/info/commandline.html)...

~~~

### `sh`

* Known as the **Bourne shell**.

* Written by **Steve Bourne**.

* Was the **default shell for Version 7 Unix**.

~~~

### `sh`

#### A Breakthrough

**First to show** that the **shell which controlled the user's interaction could be a user program** and **not a special part of the OS**.

~~~

### `csh`, `ksh`, `ohmy!`

`sh` established that a shell == a program.

The idea caught on, and more shells were developed. They each had individual strengths, but shared weaknesses:

* `sh`: great scripting, but too few features.

* `csh`: awesome features, bad scripting.

* `ksh`: improved `sh`, not open source.

~~~

### `bash`

<img src="assets/stallman.jpg" height="200">
<img src="assets/BrianJFox.png" height="200">

The Free Software Foundation writes a "from-scratch" implementation of a POSIX shell, taking all the ideas from `ksh`, and adding new features of their own, like programmable completion.

~~~

<img src="assets/bash.png" height="200" style="border: none; background: none;">

#### They call it the "Bourne again" shell ---
##### We call it `bash`!
<br>
- **Most popular shell** among users of Linux.
- **Default interactive shell** in Linux and macOS.
- Ported to Windows (Cygwin + MinGW = Git Bash)

---

### Upgrade Unix Utilities

```bash
$ brew install bash coreutils
$ echo "/usr/local/bin/bash" | sudo tee -a /etc/shells >/dev/null
```

**Restart your Terminal app**.

Run the following command. Do you receive the same output?

```bash
$ bash

bash-4.4$
```

---

<img src="assets/bash.png" style="border: none; background: none;">

### Ready? Time to Level Up!

---

#### Rock Your Readline

* `Ctrl-U` - Cuts everything to the left.
* `Ctrl-W` - Cuts the word to the left.
* `Ctrl-Y` - Pastes what's in the buffer.
* `Ctrl-A` - Go to beginning of line.
* `Ctrl-E` - Go to end of line.

<br>
To find more, simply run:

```bash
$ bind -p
```

---

#### Sudo Slip

Forget that you need elevated permissions to run a command?

Need to add `sudo` to the beginning?
<br><br>
<br>
Easy. Type `sudo !!` to invoke the last command with sudo permissions.

```bash
$ sudo !!
```

---

#### Directory Dive

Ask Thor for a **pleasant directory listing**:

```bash
bash-4.4$ ls -thor
total 4
drwxr-xr-x+   4 droxey   128B Sep 25 06:17 Public
drwx------+   3 droxey    96B Sep 25 06:17 Pictures
drwx------+   3 droxey    96B Sep 25 06:17 Movies
drwx------+   4 droxey   128B Sep 25 22:48 Music
```

~~~

Run a **second command** with the **same arguments as the first**:

```bash
$ cd /home/user/foo

cd: /home/user/foo: No such file or directory

$ mkdir !\*

mkdir /home/user/foo
```

~~~

Go **back to the last directory**:

```bash
$ cd -
```

~~~

**Create an entire directory tree** at once:

```bash
$ mkdir -p tmp/a/b/c
```

~~~

#### Find in a Codebase

```bash
$ find path_to_start | grep \\.py | xargs egrep -C3 "TODO" | less
```

~~~

---

#### Generate a Password

```bash
$ egrep -ioam1 '[a-z0-9]{8}' /dev/urandom
PKCBKhFq
```

---

#### Start a Server Anywhere

Add this line to your `~/.bashrc` and **restart your Terminal** app:

```bash
alias localserver='python -m SimpleHTTPServer 8999'
```

Now you can **serve any directory on <http://localhost:8999>** by running:

```bash
$ localserver
```

---

#### Hide Files in an Image

```bash
$ cat picture.png archive.rar > hidden_archive_in_pic.png
```

---

<img src="assets/bash.png" style="border: none; background: none;">

### Questions?
