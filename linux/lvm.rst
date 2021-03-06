###
LVM
###

Register a physical device
==========================

.. code-block:: bash

  pvcreate <dev>

Create a volumne group
======================

.. code-block:: bash

  vgcreate <vgname> <dev>


Add a new device to a volumne group
===================================

.. code-block:: bash

  vgextend <vgname> <dev>

Display all volumne groups
==========================

.. code-block:: bash

  vgdisplay

Which device is in which volumne group
======================================

.. code-block:: bash

  pvs


Just show free space of volumne groups
======================================

.. code-block:: bash

  vgs

Create a logical device
=======================

.. code-block:: bash

  lvcreate -L 10G -n <name> <vgname>

Resize a logical device
=======================

.. code-block:: bash

  lvresize -L +/-1G /dev/vgname/lvname

* Dont forget to do a resize of the filesystem
* Shrinking usually requires umounting


Create a snapshot from lvname
=============================

.. code-block:: bash

  lvcreate -L 1G -n snap --snapshot /dev/vgname/lvname


Troubleshooting
===============

* Rescan

.. code-block:: bash

  pvscan
  lvscan

* Check that volumes / volume groups are active (Attr a)

.. code-block:: bash

  lvs / pvs

* Reactivate all

.. code-block:: bash

  vgchange -ay
