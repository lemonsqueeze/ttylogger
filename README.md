## ttylogger

Simple strace-based tty logger for linux.

Handy if you need to clone another user's terminal output.

    Usage:  ttylogger pid

Use user shell's pid to trace all subsequent commands.  

For now only terminal output is replicated (no key logging). User input will show up if it's echo'ed to the terminal.

### ptrace protection

If your system has ptrace protection you might need to 

    $ sudo ttylogger pid

instead or disable ptrace protection entirely

    $ sudo echo 0 > /proc/sys/kernel/yama/ptrace_scope


### See Also

- For *BSD systems: [watch][5] 
- [ttyrpld][6]: multi-os kernel-level tty logger with (a)synchronous replay support

In case you're just looking for a way to redirect output of an already running process check out  
  [screen][1] / [reredirect][2] / [dupx][3]:   [redirecting-greping-an-existing-shells-stdout][4]



[1]: http://unix.stackexchange.com/a/281414/28431
[2]: https://github.com/jerome-pouiller/reredirect/
[3]: http://www.isi.edu/~yuri/dupx/
[4]: http://unix.stackexchange.com/questions/34806/redirecting-greping-an-existing-shells-stdout
[5]: http://www.bsdguides.org/2005/watch-terminal-activity/
[6]: http://ttyrpld.sourceforge.net/desc.php
