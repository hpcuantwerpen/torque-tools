.. _torque-host-per-line:

torque-host-per-line
====================

torque-host-per-line prints the host allocated to each task in the current Torque
job for each or a selected task group, one host per line.
The output is perfect for generating a machine file to pass to mpirun with 
the -machinefile argument, which is very useful to start a hybrid MPI program.
It is part of the torque-tools package.

Synopsis
--------

.. code-block:: bash

   torque-host-per-line [TASKGROUPNUM]

Arguments
---------

* Without arguments: Prints the hosts for each task of all task groups
  (each -L argument), one line per host (and thus per task).
  This is effectively the value of all req_information.task_usage.*.host 
  lines reported also by qstat.
* With a single numeric argument n: Prints the hosts for each task of the 
  nth task group, i.e., (n+1)st -L argument as Torque counts from 0,
  one line per host (and thus per task).
  In case the argument is not a valid task group number, i.e., larger than or
  equal to the number of task groups, nothing is printed and the exit code
  is nonzero.
* torque-host-per-line -h or --help shows help information


Examples
--------

Starting of a hybrid OpenMP/MPI program with Intel MPI: Assuming the number
of tasks in the resource request is the number of MPI ranks and lprocs is the
number of threads per MPI rank, the following lines will often work as the
core of your job script (after loading the appropriate modules including this
one and going to the right directory)

.. code-block:: bash

   export OMP_NUM_THREADS=$(torque-lprocs)
   torque-host-per-line >machinefile.$PBS_JOBID
   mpirun -machinefile machinefile.$PBS_JOBID add_name_of_executable
   /bin/rm machinefile.$PBS_JOBID

By default, mpirun will start one process per line in the machine file,
so it is not really necessary to also add -np $(torque-tasks) to the
mpirun options.
