## ttylogger

Strace-based tty logger for linux.

Handy if you need to clone another user's terminal output.

    Usage:  ttylogger pid

Use user shell's pid to trace all subsequent processes.  

Terminal output from all processes is replicated. User input will show up if it's echo'ed to the terminal.

Be aware that strace is not terribly fast at handling tons of child processes (think, very long pipes), so this will slow things down quite a bit.

For a much (much) better alternative see [ptysnoop](http://unix.stackexchange.com/a/281432/28431).
In fact the only reason to use this is that somehow you can't use ptysnoop.

### ptrace protection

If your system has ptrace protection you might need to 

    $ sudo ttylogger pid

instead or disable ptrace protection entirely:

    $ sudo echo 0 > /proc/sys/kernel/yama/ptrace_scope


### See Also

- [ptysnoop][7]
- For *BSD systems: [watch][5] 
- [ttyrpld][6]: multi-os kernel-level tty logger with (a)synchronous replay support

In case you're just looking for a way to [redirect output of an already running process][4] check out  
  [screen][1] / [reredirect][2] / [dupx][3] 

[1]: http://unix.stackexchange.com/a/281414/28431
[2]: https://github.com/jerome-pouiller/reredirect/
[3]: http://www.isi.edu/~yuri/dupx/
[4]: http://unix.stackexchange.com/questions/34806/redirecting-greping-an-existing-shells-stdout
[5]: http://www.bsdguides.org/2005/watch-terminal-activity/
[6]: http://ttyrpld.sourceforge.net/desc.php
[7]: http://unix.stackexchange.com/a/281432/28431

