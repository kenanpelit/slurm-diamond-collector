#slurm-diamond-collectors

A collection of custom [diamond](http://diamond.readthedocs.io/en/latest/ "Diamond Docs") collectors to gather various [slurm](http://www.schedmd.com/ "Slurm") stats.

##Description

These collectors are intended to be used with diamond to ship stats to [graphite](http://graphite.wikidot.com/ "Graphite").  Each collector collects data on a different aspect of slurm.  Feel free to add or update these collectors to suit your needs.

###SlurmSchedStatsCollector

This collector is a diamond version of this:

http://giovannitorres.me/graphing-sdiag-with-graphite.html

As described in the above page it will require you to install [pyslurm](https://github.com/PySlurm/pyslurm "PySlurm").  This collector will collect [sdiag](http://slurm.schedmd.com/sdiag.html "sdiag") stats allowing you to chart your scheduler performance over time.

###SlurmSshareCollector

This collector grabs the current [sshare](http://slurm.schedmd.com/sshare.html "sshare") data for users.  This assumes that you are using a two tier simple [fairshare](http://slurm.schedmd.com/priority_multifactor.html "Multifactor Priority") system of accounts and users of those accounts.

###SlurmClusterStatusCollector

This collector pulls the current [state](http://slurm.schedmd.com/scontrol.html "scontrol") of all the nodes in the cluster and then computes overall stats of the cluster such as number of nodes down, number of nodes in use, etc.

##Usage

Simply add them to `/usr/share/diamond/collectors` and then activate them in diamond and you should be good to go.