################
Shell Scripting
################

Sequence
========

.. code-block:: bash

  for i in {1..32}; do echo $i; done

Calculation
===========

.. code-block:: bash

  x=3
  y=$(($x+4))


Quote Spaces in Filenames
==========================

.. code-block:: bash

  echo $FILE | sed 's/ /\\ /g'


Remove lines beginning with XXX
===============================

.. code:: bash

  sed -i -e '/^XXX_/d' /my/file"


Get yesterdays date
===================

.. code-block:: bash

  date +%Y:%m:%d -d "1 day ago"


Now in unix time
================

.. code-block:: bash

  date +%s -d "now"

Find files modified after date
==============================

.. code-block:: bash

  find . -type f -newermt 2012-12-24

Get lines where the nth element is bigger than x
=================================================

.. code-block:: bash

  perl -n -e '@a=split(/\s/,$_); print $_ if $a[3] > 2;'

Generate a random number
========================

.. code-block:: bash

  echo $RANDOM
