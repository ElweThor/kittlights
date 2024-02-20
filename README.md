# kittlights
lights changing on your server's keyboard, to make you and others know it's alive

 Simulates the (in)famous David Hasselhoff's[1] KITT[2] supercar's[3] front
lights on the keyboard in tty12 to show that the server is operational, like
old mainframes did: useful when the monitor is permanently switched off.

**Note**: to make this utility being automatically started at system's boot
      use the insserv(8) utility on /etc/init.d/kittlights, which is a
      custom script built to avoid hanging the system by the daemon it
      starts ('cause of the daemon's infinite loop).

**Why tty12**: I wrote this little utility to remember whoever got around the
      server that it was RUNNING, so to avoid switching it off pulling the
      power cable, cleaning it's keyboard and so on.
       As I'm used to configure syslog's facility to show all it's records
      to tty12 (so, when something goes wrong, like having an OOPS, I've just
      to switch server's monitor on), I directed this script's output there (but
      you can configure to have it at the tty you prefer, of course).

 This is a monolithic all-in-one utility, with just a defaults starting
parameters file (look into /etc/defaults/) and a (modified) starter script
to make it to start at system's boot (look into /etc/init.d/)

20090131 - Luca "Sky" Coianiz

 **Additional note**, *to Git downloaders*: this utility have been developed into a
SUSE-based linux distro (maybe 6.0 or 8.0, I don't remember), then ported (and
currently running) into a Debian 3.16 one.
 I'm not keeping it up to date with different/current init mechanisms: just looking
that, on my system, the tool correctly works.

 *Just a final note*: even if infinite-looping, it uses *nearly no CPU time*, 'cause
of the 1 sec. "**sleep**" between actions (of course tailorable to your needs): if you
omit the sleep, you most probably force the system to execute a *tight loop*, ending
by using 100% CPU. To the other side, that will make the "scanning lights" effect
totally unuseful.

**Refs**

[1] https://en.wikipedia.org/wiki/David_Hasselhoff

[2] https://en.wikipedia.org/wiki/KITT

[3] https://en.wikipedia.org/wiki/Knight_Rider_%281982_TV_series%29
