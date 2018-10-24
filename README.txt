This directory contains a number of tools developed to make it easier to 
start parallel jobs on the UAntwerp clusters using the version 2 aka
NUMA-aware syntax of Torque. The tools can also help to make the core
of job scripts more independent from the actual resource request string
so that job scripts can be easily reused with different resources
without having to change the core code of the script.

Contact hpc@uantwerpen.be if you find bugs or want to propose extensions
to this toolset.

All tools are documented through manual pages. The page torque-tools(1)
lists all tools and is the ideal starting point.

On the GitHub pages of this project,
https://github.com/hpcuantwerpen/torque-tools,
a sample EasyBuild config file is available. As this it currently uses
the Tarball EasyBlock, we have not included it in the distribution files
as otherwise it would be copied to the install directories. This also keeps
things clean for non-EasyBuild users.
