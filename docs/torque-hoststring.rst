.. _torque-hoststring:

torque-hoststring
=================

.SH DESCRIPTION
torque-hoststring prints the host allocated to each task in the current Torque job
for each or a selected task group, column-separated on a single line.
It is part of the torque-tools package.

Synopsis
--------

.. code-block:: bash

   torque-hoststring [TASKGROUPNUM]

Arguments
---------

* Without arguments: Prints the hosts for each task of all task groups
  (each -L argument), in a comma-separated list without spaces.
  This is effectively the value of all req_information.task_usage.*.host
  lines reported also by qstat.,
* With a single numeric argument n: Prints the hosts for each task of the 
  nth task group, i.e., (n+1)st -L argument as Torque counts from 0,
  in a comma-separated list without spaces.
  In case the argument is not a valid task group number, i.e., larger than or
  equal to the number of task groups, nothing is printed and the exit code
  is nonzero.
* torque-hoststring -h or --help shows help information
