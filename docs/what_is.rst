What is it?
===========

torque-tools provides a set of tools to query job information from Torque and
is specifically meant for job scripts that use the version 2 resource syntax
(aka NUMA-aware) syntax from Torque. The purpose is to offer a set of tools
that help to make the core of job scripts as independent from the actual
resource request as possible to ease reuse of scripts with a different 
node/core configuration. They can also be used to get a list of hosts
in the allocation in formats suitable for various programs, such as
mpirun (in particular for hybrid applications where mpirun fails to 
get sufficient information from Torque), charm++ applications or 
GNU parallel.

Commands
--------

* :doc:`torque-tasks`: Prints the number of tasks in the current Torque job for each or a selected task group.
* :doc:`torque-lprocs`: Prints the number of lprocs per task in the current Torque job for each or a selected task group.
* :doc:`torque-host-per-line`: Prints for each task in all or a selected task group
  the assigned host, one per line. When stored in a file, the output can be
  used with mpirun -machinefile to start hybrid applications.
* :doc:`torque-hoststring`: Prints for each task in all or a selected task group the
  assigned host, as a comma-separated string of hosts for each task. 
* :doc:`torque-hosts-parallel`: Generates a host list in the format required by GNU
  parallel. Currently this command does not yet support the generation of
  an individual host list for a single task group.