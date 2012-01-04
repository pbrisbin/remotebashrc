# RemoteBashRC

## What is it?

As per justyns:

> I work doing tech support for a dedicated server hosting company. So 
> naturally, we deal with lots of servers every day, and one of the guys 
> I work with said something like “I wish all my aliases would follow me 
> to other servers”. That sounded like a cool idea to me, and basically 
> explains what the script does.

## Usage

    /path/to/script user@host [port]

## Why fork?

I originally thought this could be accomplished more simply by reading 
the local bashrc into the `ssh` process's `stdin`, then `cat`ting it out 
to the temp location before starting the shell.

After numerous attempts, I've learned that this is very hard. Utilizing 
`stdin` for the data renders `ssh` unable to give you a shell. I'm still 
hoping to get this route working; but for now, I've just slimmed down 
the script a little so things are more straight forward and less chatty. 

Anyone who wants to solve this puzzle given the following (arbitrary) 
restraints is more than welcome:

1. Don't call ssh more than once.
2. Don't call scp or sftp or any other tool networking tool to send the 
   file separately.
3. Accept and use any and all valid ssh options.
4. Don't change the behavior of ssh (i.e. adding Control files).
5. Don't setup any ad-hoc shared network storage.
