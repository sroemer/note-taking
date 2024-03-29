# Bash



## Keyboard Shortcuts



### Command Editing Shortcuts

- C  trl + a      go to the start of the command line
- Ctrl + e      go to the end of the command line
- Ctrl + k      delete from cursor to the end of the command line
- Ctrl + u      delete from cursor to the start of the command line
- Ctrl + w      delete from cursor to start of word (i.e. delete backwards one word)
- Ctrl + y      paste word or text that was cut using one of the deletion shortcuts (such as the one above) after the cursor
- Ctrl + xx     move between start of command line and current cursor position (and back again)
- Alt + b       move backward one word (or go to start of word the cursor is currently on)
- Alt + f       move forward one word (or go to end of word the cursor is currently on)
- Alt + d       delete to end of word starting at cursor (whole word if cursor is at the beginning of word)
- Alt + c       capitalize to end of word starting at cursor (whole word if cursor is at the beginning of word)
- Alt + u       make uppercase from cursor to end of word
- Alt + l       make lowercase from cursor to end of word
- Alt + t       swap current word with previous
- Ctrl + f      move forward one character
- Ctrl + b      move backward one character
- Ctrl + d      delete character under the cursor
- Ctrl + h      delete character before the cursor
- Ctrl + t      swap character under cursor with the previous one



### Command Recall Shortcuts

- Ctrl + r      search the history backwards
- Ctrl + g      escape from history searching mode
- Ctrl + p      previous command in history (i.e. walk back through the command history)
- Ctrl + n      next command in history (i.e. walk forward through the command history)
- Alt + .       use the last word of the previous command



### Command Control Shortcuts

- Ctrl + l      clear the screen
- Ctrl + s      stops the output to the screen (for long running verbose command)
- Ctrl + q      allow output to the screen (if previously stopped using command above)
- Ctrl + c      terminate the command
- Ctrl + z      suspend/stop the command



### Bash Bang (!) Commands

- !!            run last command
- !/word/       run the most recent command that starts with /word/ (e.g. !ls)
- !/word/:p     print out the command that \!/word/ would run (also adds it as the latest command in the command history)
- !$            the last word of the previous command (same as Alt + .)
- !$:p          print out the word that \!\$ would substitute
- !*            the previous command except for the last word
- !*:p          print out what \!\* would substitute



## Conditional statements



### if
```
if [[ condition ]]; then
    ...
elif [[ condition ]]; then
    ...
else
    ...
fi
```



## Control flow



### for
```
for i in range; do
    ...
done
```



### while
```
while condition; do
    ...
done
```



## Special Variables

- $0: the command running
- $1-$n: argument 1 - n
- $@: list of all arguments
- $#: number of arguments
- $*: all arguments separated by IFS (use $@ to avoid whitespace issues)
- $$: process id of the shell the command is running in
- $?: exit code of previous command
- $!: process id of most recent background process
- $IFS: the internal field separator



## Conditional expressions

- -a file            True if file exists.
- -b file            True if file exists and is a block special file.
- -c file            True if file exists and is a character special file.
- -d file            True if file exists and is a directory.
- -e file            True if file exists.
- -f file            True if file exists and is a regular file.
- -g file            True if file exists and its set-group-id bit is set.
- -h file            True if file exists and is a symbolic link.
- -k file            True if file exists and its "sticky" bit is set.
- -p file            True if file exists and is a named pipe (FIFO).
- -r file            True if file exists and is readable.
- -s file            True if file exists and has a size greater than zero.
- -t fd              True if file descriptor fd is open and refers to a terminal.
- -u file            True if file exists and its set-user-id bit is set.
- -w file            True if file exists and is writable.
- -x file            True if file exists and is executable.
- -G file            True if file exists and is owned by the effective group id.
- -L file            True if file exists and is a symbolic link.
- -N file            True if file exists and has been modified since it was last read.
- -O file            True if file exists and is owned by the effective user id.
- -S file            True if file exists and is a socket.
- file1 -ef file2    True if file1 and file2 refer to the same device and inode numbers.
- file1 -nt file2    True if file1 is newer (according to modification date) than file2, or if file1 exists and file2 does not.
- file1 -ot file2    True if file1 is older than file2, or if file2 exists and file1 does not.
- -o optname         True if the shell option optname is enabled. The list of options appears in the description of the -o option to the set builtin (see The Set Builtin).
- -v varname         True if the shell variable varname is set (has been assigned a value).
- -R varname         True if the shell variable varname is set and is a name reference.
- -z string          True if the length of string is zero.
- -n string          True if the length of string is non-zero.
- string1 == string2
  string1 = string2  True if the strings are equal.
                     When used with the \[\[ command, this performs pattern matching
                     '=' should be used with the test command for POSIX conformance.
- string1 != string2 True if the strings are not equal.
- string1 < string2  True if string1 sorts before string2 lexicographically.
- string1 > string2  True if string1 sorts after string2 lexicographically.
- arg1 OP arg2       OP is one of '-eq', '-ne', '-lt', '-le', '-gt', or '-ge'.
