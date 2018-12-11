.. _torque-lprocs:

torque-lprocs
=============

torque-lprocs prints the number of lprocs per task in the current Torque job
for each or a selected task group.

Synopsis
--------

.. code-block:: bash

   torque-lprocs [TASKGROUPNUM]


Arguments
---------

* Without arguments: Prints the number of lprocs for each task
  group (each -L argument). This is effectively the value of all 
  req_information.lprocs lines reported also by qstat.
* With a single numeric argument n: Prints the number of tasks for the 
  nth task group, i.e., (n+1)st -L argument as Torque counts from 0.
  This is effectively the value also reported for req_information.lprocs.n.
  In case the argument is not a valid task group number, i.e., larger than or
  equal to the number of task groups, nothing is printed and the exit code
  is nonzero.
* torque-lprocs -h or --help shows help information
