.. _whatsnew-4.4:

===================================
 What's new in Celery 4.4 (Cliffs)
===================================
:Author: Asif Saif Uddin (``auvipy at gmail.com``)

.. sidebar:: Change history

    What's new documents describe the changes in major versions,
    we also have a :ref:`changelog` that lists the changes in bugfix
    releases (0.0.x), while older series are archived under the :ref:`history`
    section.

Celery is a simple, flexible, and reliable distributed programming framework
to process vast amounts of messages, while providing operations with
the tools required to maintain a distributed system with python.

It's a task queue with focus on real-time processing, while also
supporting task scheduling.

Celery has a large and diverse community of users and contributors,
you should come join us :ref:`on IRC <irc-channel>`
or :ref:`our mailing-list <mailing-list>`.

To read more about Celery you should go read the :ref:`introduction <intro>`.

While this version is backward compatible with previous versions
it's important that you read the following section.

This version is officially supported on CPython 2.7, 3.5, 3.6, 3.7 & 3.8
and is also supported on PyPy2 & PyPy3.

.. _`website`: http://celeryproject.org/

.. topic:: Table of Contents

    Make sure you read the important notes before upgrading to this version.

.. contents::
    :local:
    :depth: 2

Preface
=======

The 4.4.0 release continues to improve our efforts to provide you with
the best task execution platform for Python.

This release has been codenamed `Cliffs <https://www.youtube.com/watch?v=i524g6JMkwI>`_
which is one of my favorite tracks.

This release focuses on mostly bug fixes and usability improvement for developers.
Many long standing bugs, usability issues, documentation issues & minor ehancement
issues were squash squashed which improve the overall developers experience.

Celery 4.4 is the first release to support Python 3.8 & pypy36-7.2.

As we now begin to work on Celery 5, the next generation of our task execution
platform, at least another 4.x is expected before Celery 5 stable release & will
get support for at least 1 years depending on community demand and support.

We have also focused on reducing contribution friction and updated the contributing
tools.



*— Asif Saif Uddin*

Wall of Contributors
--------------------

.. note::

    This wall was automatically generated from git history,
    so sadly it doesn't not include the people who help with more important
    things like answering mailing-list questions.


Upgrading from Celery 4.3
=========================

Please read the important notes below as there are several breaking changes.

.. _v440-important:

Important Notes
===============

Supported Python Versions
-------------------------

The supported Python Versions are:

- CPython 2.7
- CPython 3.5
- CPython 3.6
- CPython 3.7
- CPython 3.8
- PyPy2.7 7.2 (``pypy2``)
- PyPy3.5 7.1 (``pypy3``)
- PyPy3.6 7.2 (``pypy3``)

Dropped support for Python 3.4
------------------------------

Celery now requires either Python 2.7 or Python 3.5 and above.

Python 3.4 has reached EOL in March 2019.
In order to focus our efforts we have dropped support for Python 3.4 in
this version.

If you still require to run Celery using Python 3.4 you can still use
Celery 4.3.
However we encourage you to upgrade to a supported Python version since
no further security patches will be applied for Python 3.4.

Kombu
-----

Starting from this release, the minimum required version is Kombu 4.6.6.

Billiard
--------

Starting from this release, the minimum required version is Billiard 3.6.1.

Redis Message Broker
--------------------

Due to multiple bugs in earlier versions of py-redis that were causing
issues for Celery, we were forced to bump the minimum required version to 3.3.0.

Redis Result Backend
--------------------

Due to multiple bugs in earlier versions of py-redis that were causing
issues for Celery, we were forced to bump the minimum required version to 3.3.0.

.. _v440-news:

News
====

Result Backends
---------------

ElasticSearch Result Backend HTTP Basic Authentication Support
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can now use HTTP Basic Authentication when using the ElasticSearch result
backend by providing the username and the password in the URI.

Previously, they were ignored and only unauthenticated requests were issued.
