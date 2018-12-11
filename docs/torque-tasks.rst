.. _torque-tasks:

torque-tasks
============

torque-tasks prints the number of tasks in the current Torque job for each
or a selected task group.

Synopsis
--------

.. code-block:: bash

   torque-tasks [TASKGROUPNUM]
    
Arguments
---------

* Without arguments: Prints the number of tasks for each task
  group (each -L argument). This is effectively the value of all 
  req_information.task_count lines reported also by qstat.
* With a single numeric argument n: Prints the number of tasks for the 
  nth task group, i.e., (n+1)st -L argument as Torque counts from 0.
  This is effectively the value also reported for req_information.task_count.n. 
  In case the argument is not a valid task group number, i.e., larger than or
  equal to the number of task groups, nothing is printed and the exit code
  is nonzero.
* torque-tasks -h or --help shows help information
