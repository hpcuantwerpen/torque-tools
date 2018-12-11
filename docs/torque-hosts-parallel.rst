.. _torque-hosts-parallel:


torque-hosts-parallel
=====================

.SH DESCRIPTION
torque-hosts-parallel is an experimental tool to generate a hostlist 
(as a single string) that can be used for the -S argument of GNU parallel.
It is part of the torque-tools package.

Synopsis
--------

.. code-block:: bash

   torque-hosts-parallel

Arguments
---------

The current experimental implementation does not support command line options.

Example
-------

In a Torque job or interactive job, after loading the appropriate modules
(parallel for GNU parallel and the torque-tools module), try:

.. code-block:: bash

   seq 1 $(torque-host-per-line | wc -l) | parallel -S $(torque-hosts-parallel) -q bash -c 'echo "$HOSTNAME"'

Or to see what the line looks like, simply execute:

.. code-block:: bash

   torque-hosts-parallel

or

.. code-block:: bash

   echo $(torque-hosts-parallel)


Comments
--------

We're interested in ways people would use this so that we can further extend
the command as needed. Pleace contact hpc@uantwerpen.be.