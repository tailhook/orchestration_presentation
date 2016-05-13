.. role:: frag
   :class: fragment

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

* Documents commands
* IDE folders with deps
* Versioning
* Continuous Integration



