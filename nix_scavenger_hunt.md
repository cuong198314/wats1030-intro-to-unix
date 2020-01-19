# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* /c/Users/CCC/wats 3030

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* cuongm.github.io/  wats1030-intro-to-unix/

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* total 24K
drwxr-xr-x 1 CCC 197121 0 Jan 18 16:50 ./
drwxr-xr-x 1 CCC 197121 0 Jan 18 17:35 ../
drwxr-xr-x 1 CCC 197121 0 Jan 14 17:39 cuongm.github.io/
drwxr-xr-x 1 CCC 197121 0 Jan 18 16:49 wats1030-intro-to-unix/

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?* man ls Display the manual page for the item (program) ls. -a, --all do not ignore entries starting with .  -l use a long listing format , -h human-readable

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?* bin/  cmd/  dev/  etc/  git-bash.exe*  git-cmd.exe*  LICENSE.txt  mingw64/  proc/  ReleaseNotes.html  tmp/  unins000.dat  unins000.exe*  unins000.msg  usr/

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:* C:/Program Files/Git


* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*/c/Users/CCC

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?* 3
* Press the up arrow on your keyboard. *What just happened?* ls
* Press the up arrow a few more times. *What do you see?*pwd
* Run the `history` command. *What do you see?* the list of all the commands that have been used, a total of 152 commands

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?* CCC
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:* none
* How long has your system been running? Use `uptime` to see, and *paste the result here:* command not found
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?* a list of all the processes in the system for all users
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?* command not found

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* two
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*  I have to type 'start' to open the file, the date is 01-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?* ./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* two
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.* serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.


### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* a list of user file, one demo file, 
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* a new command window pop up, cmd.exe
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
     2326       1    2326       1572  ?         197609 18:32:11 /usr/bin/mintty
     2327    2326    2327       7496  pty0      197609 18:32:11 /usr/bin/bash
     2088       1    2088       5960  cons0     197609 17:09:11 /usr/bin/bash
     2453    2327    2453      18048  pty0      197609 19:20:38 /usr/bin/ps

