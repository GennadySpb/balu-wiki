########
Postgres
########

Create a database
==================

.. code-block:: bash

  createdb mydb -E UTF8 -O myuser

* or

.. code-block:: bash

  CREATE DATABASE mydb WITH OWNER mypuser;

* By default this will copy template1 db


Create a user
==============

.. code-block:: bash

  createuser --password myuser

* or

.. code-block:: bash

  CREATE USER myuser WITH password 'secret';


Change user password
=====================

.. code-block:: bash

  ALTER USER myuser WITH PASSWORD 'moresecret';

Change user permissions
========================

.. code-block:: bash

  ALTER USER myuser CREATEDB;

Delete user
============

.. code-block:: bash

  dropuser myuser


* or

.. code-block:: bash

  DROP USER myuser

List databases
===============

.. code-block:: bash

  \l

Connect to a database
======================

.. code-block:: bash

  \c <db>

List all tables
================

.. code-block:: bash

  \dt


Describe table
==============

.. code-block:: bash

  \d+ table


List user and permissions
==========================

.. code-block:: bash

  \du


Show active connections
=======================

.. code-block:: bash

  SELECT * FROM pg_stat_activity;


Export select as CSV
====================

.. code-block:: bash

  copy(select * from table) to '/some/file' with csv header;


Import CSV
==========

.. code-block:: bash

  copy table from '/some'file' with csv header;
