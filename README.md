# Dotfiles
There are many hidden files in the land of bash.  
However I have edited some files to make my life a bit easier, and added one to make my life more difficult.  
These files can be found in this repo as well as the explanation/edits in this very readme.

## Alias
In my _root directory_ which you can of course get to by doing ``cd ~`` I have a hidden file called _.bash_aliases_.  
You can of course find this yourself by using the command ``ls -a`` to show all files, even the hidden ones.  
I have edited this file to do several things.  

1. Name alias  

My name, as you might have guessed is _Daniel_.
So when I type my name I'd like to have my _bash_ tell me that it likes me.  
Why? Because it's almost Valentines and I really need that positive reinforcement.  
I used ``nano .bash_aliases`` to open this file.  
I added the line ``alias Daniel='cowsay Daniel? heard of him, cool guy.'``  
So now whenever I type ``Daniel`` I get a cow that tells me I'm a cool guy.  
(If you for some reason get an error message about the command ``cowsay`` you probably need to install it.)

2. Sudo alias

I like when stuff works.  
I like it so much that I sometimes get a bit agitated when it doesn't.  
Thats why I made an alias called ``alias fucking='sudo'`` so whenever I ask _bash_ to ``fucking do something`` it will.  

## Prompt

My prompt is shamelessly stolen from a different developer.  
Why? Because I messed around a bit before realising that there are people way smarter than me who have worked with this program for longer than I can possible imagine.  
That's why I took inspiration from others by adding several things like "Jobs" which is the current open/running programs and adding a line counter.   
I'm not quite sure if this is handy, but time will tell.  
The only thing I do need to add is a tracker for my GH to check what branch/if it's up to date. But that'll come later on.
Here's the current value of PS1 which I added to the bottom of my _.bashrc_ file with ``>>``  
``PS1="\n\[\e[32;1m\](\[\e[37;1m\]\u\[\e[32;1m\])-(\[\e[37;1m\]jobs:\j\[\e[32;1m\])-(\[\e[37;1m\]\w\[\e[32;1m\])\n(\[\$``  

## Welcome message

Now for a welcome message I went a bit overboard.  
According to StackOverflow (yes I know) it was better to create your own bash script for all users, so I did.  
It starts with ``cd /`` to get to our location, from there we move to ``cd etc/profile.d``. This can of course be executed in one command, but I like knowing when I go up or down.  
Here I made my own bash script using ``sudo touch greeting.sh`` which I opened with nano ``sudo nano greeting.sh``  
In this I used several different things that are anything but useful.  
First I used ``fortune`` which print out a fortune. I added ``-s`` to it so it would stick to short messages only.  
Then I used a `` | `` to pipe it to ``cowsay`` then I forced it to take a random cow from the available ones using ``-f `ls -1 /usr/share/cowsay/cows | sort -R | head -1` -n``  
Are you still paying attention? Good.  
Then I added rainbow colour effects to it, because that was the last thing it needed.  
This creates the beautiful line of code in _greeting.sh_ which is in full:  
``fortune | cowsay -s -f `ls -1 /usr/share/cowsay/cows/ | sort -R | head -1` -n | lolcat``  
You can of course add an ``-a`` to the end of the lolcat to fully animate it, if you so desire.

## The end
And that brings us to the sad conclusion of this readme.  
I hope you learned to not follow in my footsteps and instead create something that works for you.  
Have a great day!
