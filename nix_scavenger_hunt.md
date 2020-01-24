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

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. 
Users/campbellchr1/projects/wats1030-intro-to-unix


* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. LICENSE                         challenge_files                 nix_scavenger_hunt_stretch.md
README.md                       nix_scavenger_hunt.md           super_scavengers.md


* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. 
It gives me the time and date of my clone, the size of each file and then some other information that I'm unclear of.


* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
man ls -a =    Include directory entries whose names begin with a dot (.).
man ls -l =   (The lowercase letter ``ell''.)  List in long format.  (See below.)  If the output is
             to a terminal, a total sum for all the file sizes is output on a line before the long
             listing.
man ls -h = When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte,
             Terabyte and Petabyte in order to reduce the number of digits to three or less using
             base 2 for sizes.             

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
Applications                    Volumes                         net
Library                         bin                             opt
Network                         cores                           private
Quarantine                      dev                             sbin
System                          etc                             tmp
User Information                home                            usr
Users                           installer.failurerequests       var


* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

PAVL050X-H1ZLFV:/ campbellchr1$ 


* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

/Users/campbellchr1

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
2015_special_stuff.demo         cloaked-wookie.demo             scooter-double-mamba.demo


* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
* Press the up arrow on your keyboard. *What just happened?*
* Press the up arrow a few more times. *What do you see?*
* Run the `history` command. *What do you see?*

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
campbellchr1


* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
campbellchr1 console  Jan  7 19:03 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

18:28  up 5 days, 23:26, 1 user, load averages: 5.34 3.56 3.47


* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
It provides information about the currently running processes


* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
It displays information about CPU and memory utilization

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
2

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
01-15-2015

* Use the `find` command to search for fpwiles more effectively.f Search the sub-directories under `challenge_files` to find the location of the file named modi_laboriosam.txt. *Where is that file located?*
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* 
2


* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

A whole lot of _special_stuff

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
Files dates and size

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

campbellchr1      540  87.0  0.2  1678684  39828   ??  R     7Jan20 2717:30.42 /Applications/Adobe Acrobat XI Pro/Adobe Acrobat Pro.app/Contents/MacOS/AdobeAcrobat -psn_0_57358
campbellchr1    53953  58.6  3.3  3644356 555644   ??  R    Fri09AM 103:06.14 /Applications/Google Chrome.app/Contents/Frameworks/Google Chrome Framework.framework/Versions/79.0.3945.117/Helpers/Google Chrome Helper (Renderer).app/Contents/MacOS/Google Chrome Helper (Renderer) --type=renderer --field-trial-handle=1718379636,12513205730580963720,13260020478757892734,131072 --lang=en-US --metrics-client-id=1adf9016-43c5-4600-a172-dac13fb806ff --disable-oor-cors --enable-auto-reload --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=7021424241027753691 --renderer-client-id=945 --no-v8-untrusted-code-mitigations --seatbelt-client=349
campbellchr1      571   8.6  0.3  4507128  55580   ??  R     7Jan20 139:49.99 /Applications/Google Chrome.app/Contents/Frameworks/Google Chrome Framework.framework/Versions/79.0.3945.117/Helpers/Google Chrome Helper (GPU).app/Contents/MacOS/Google Chrome Helper (GPU) --type=gpu-process --field-trial-handle=1718379636,12513205730580963720,13260020478757892734,131072 --metrics-client-id=1adf9016-43c5-4600-a172-dac13fb806ff --gpu-preferences=KAAAAAAAAAAgAAAAAAAAAAAAYAAAAAAAEAAAAAAAAAAAAAAAAAAAAOgAAAAcAAAA4AAAAAAAAADoAAAAAAAAAPAAAAAAAAAA+AAAAAAAAAAAAQAAAAAAAAgBAAAAAAAAEAEAAAAAAAAYAQAAAAAAACABAAAAAAAAKAEAAAAAAAAwAQAAAAAAADgBAAAAAAAAQAEAAAAAAABIAQAAAAAAAFABAAAAAAAAWAEAAAAAAABgAQAAAAAAAGgBAAAAAAAAcAEAAAAAAAB4AQAAAAAAAIABAAAAAAAAiAEAAAAAAACQAQAAAAAAAJgBAAAAAAAAoAEAAAAAAACoAQAAAAAAALABAAAAAAAAuAEAAAAAAAAQAAAAAAAAAAAAAAAAAAAAEAAAAAAAAAAAAAAABgAAABAAAAAAAAAAAAAAAAcAAAAQAAAAAAAAAAAAAAAIAAAAEAAAAAAAAAAAAAAACgAAABAAAAAAAAAAAAAAAAsAAAAQAAAAAAAAAAAAAAANAAAAEAAAAAAAAAABAAAAAAAAABAAAAAAAAAAAQAAAAYAAAAQAAAAAAAAAAEAAAAHAAAAEAAAAAAAAAABAAAACAAAABAAAAAAAAAAAQAAAAoAAAAQAAAAAAAAAAEAAAALAAAAEAAAAAAAAAABAAAADQAAABAAAAAAAAAABAAAAAAAAAAQAAAAAAAAAAQAAAAGAAAAEAAAAAAAAAAEAAAABwAAABAAAAAAAAAABAAAAAgAAAAQAAAAAAAAAAQAAAAKAAAAEAAAAAAAAAAEAAAACwAAABAAAAAAAAAABAAAAA0AAAAQAAAAAAAAAAYAAAAAAAAAEAAAAAAAAAAGAAAABgAAABAAAAAAAAAABgAAAAcAAAAQAAAAAAAAAAYAAAAIAAAAEAAAAAAAAAAGAAAACgAAABAAAAAAAAAABgAAAAsAAAAQAAAAAAAAAAYAAAANAAAA --service-request-channel-token=17170484408683337788
s campbellchr1$ 