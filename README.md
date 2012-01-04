# RemoteBashRC

## What is it?

As per justyns:

> I work doing tech support for a dedicated server hosting company. So 
> naturally, we deal with lots of servers every day, and one of the guys 
> I work with said something like “I wish all my aliases would follow me 
> to other servers”. That sounded like a cool idea to me, and basically 
> explains what the script does.

I took his original idea and pretty much completely rewrote the thing. 

Not that it was bad, I just already use persistent connections myself 
and thought that it would be simpler if you just `cat` your bashrc into 
the ssh program and let it write out the bashrc on the other side before 
launching the shell.

I also wanted this program to be a stand-in for ssh, so I pass all the 
options through as is.

## How to use it?

Use the script in place of ssh in any way you wish. I prefer the usage 
be transparent, so I do something like:

    # create a local bin and put in the front of the path so it's 
    # programs take precendence.
    mkdir ~/bin
    export PATH=$HOME/bin:$PATH

    # then create a custom ssh there
    cp remotebashrc ~/bin/ssh

Then just use ssh as normal.

## Options

`--tmpfile` and `--rcfile` will be accepted as options to the script. 
They determine where to write the bashrc file on the remote and where to 
read it on the local respectively.

All other options are assumed to be for `ssh` and will be passed through 
directly.
