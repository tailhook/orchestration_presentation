.. role:: frag
   :class: fragment

.. role:: kill
   :class: kill

Orchestration
=============


Agenda
======

* :frag:`What is orchestration?`
* :frag:`What we have built?`
* :frag:`Plans`


Topics
======

* :frag:`Architecture`
* :frag:`Why not docker?`
* :frag:`Why not kubernetes/mesos/...?`
* :frag:`Why rust?`

Orchestration
=============

* :frag:`Auto-Deployment`
* :frag:`Scheduling`
* :frag:`Monitoring`
* :frag:`Self-Healing`


Requirements
============

* :frag:`Minimum components`
* :frag:`Availability first`
* :frag:`Introspection`
* :frag:`Minimum configuration`


Minimum Configuration
=====================

* :frag:`Only One Orchestration`
* :frag:`Security`
* :frag:`Duplication`


Minimum Components
==================

* :frag:`Network Async and Lossy`
* :frag:`Leader Election`


Introspection
=============

.. container:: fragment

    .. class:: fragment fade-in strike

       Logs

       Metrics

.. container:: fragment

    Fine-grained States


Availability First
==================

* :frag:`Restart Process`
* :frag:`Scheduling in Failing Mode`


Requirements
============

* Minimum components
* Availability first
* Introspection
* Minimum configuration


What we have?
=============

* vagga
* lithos
* cantal
* verwalter


Vagga
=====

Containers for dev.env.


Vagga
=====

.. code-block:: console

    $ git clone git@host:proj
    $ cd proj
    $ vagga
    Available commands:
      run   Start app with postgres and redis
      doc   Build docs with sphinx
      test  Run unit tests
      js    Compile javascripts


Example 1 
=========

.. code-block:: console

    $ vagga run
    Okay, server started at http://localhost:8080


Example 2
=========

.. code-block:: console

    $ vagga doc
    Installing sphinx
    ...
    Docs are built in doc/_build/html/index.html

Example 3
=========

.. code-block:: console

    $ git pull
    $ vagga test
    Requirements txt changed
    Rebuilding container "test"
    ................
    Ok 20 successful

Vagga
=====

* Self-documentation
* IDE folders with deps
* Versioning
* Continuous Integration


Lithos
======

Production-grade containers


Lithos
======

* Start process
* Set up environment
* Mount file systems
* Restart on failure


Lithos
======

* No Downloading
* No Build
* No Network API

Lithos
======

Configuration files

.. class:: fragment

   introspection

   security

Lithos: Security
================

* :frag:`Sandbox config`
* :frag:`Read-only/nosuid/noexec`
* :frag:`Fixed command-line (*)`

.. class:: fragment small

    (*) You control only version and numer of instances

Lithos: Day 0
=============

* :frag:`Upgrade w/o restart`
* :frag:`PID 1`


Cantal
======

Monitoring

Metrics


Cantal
======

* :frag:`System metrics`
* :frag:`CGroups`
* :frag:`Application metrics`


Cantal
======

* :frag:`2 sec scan interval`
* :frag:`1 hour in-memory`
* :frag:`Web UI`
* :frag:`-> Carbon(graphite) -> Graphana`


Cantal: Network
===============

* :frag:`Peer discovery`
* :frag:`Aggregated stats`


Cantal: Rust
============

.. class:: fragment

   3k-10k metrics in 10-40ms

   1h in 15-35MiB

.. class:: fragment kill

   Debug build

