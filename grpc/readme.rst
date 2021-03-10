Java gRPC Applications
#################

This folder includes gRPC framework demo applications written in Java.

-----

.. contents::

.. section-numbering::

Usage
=====

Launching
---------

Docker-compose
~~~~~~~~~~~~~~

| An agent will be downloaded from the configured manager for each application before running.
| Depending on your machine, full environment startup may take a couple of minutes.
| Do the following steps:
|

* Start a local IAST manager instance
* Edit the provided ``.env`` file if needed or use ``.env.linux`` file in linux
* Set ``IAST_MANAGER_URL=http://host.docker.internal:8380`` manually in the relevant docker-compose.yml file

.. code-block:: bash

    # Windows
    # pull latest:
    docker-compose -f docker-compose-java-grpc.yml pull
    # start:
    docker-compose -f docker-compose-java-grpc.yml up -d
    # stop:
    docker-compose -f docker-compose-java-grpc.yml down

    # Linux
    # pull latest:
    sudo docker-compose -f docker-compose-java-grpc.yml pull
    # start:
    sudo docker-compose -f docker-compose-java-grpc.yml --env-file .env.linux up -d
    # stop:
    sudo docker-compose -f docker-compose-java-grpc.yml down


Flow Triggering
---------------


To trigger gRPC flows you can sent request to ``8121/grpc/send?message=${text}``:
Replace *${text}* with the following input to get the relevant vulnerability:

* *sqli* -> SQL injection
* *commandi* -> Command injection
* *random* -> Weak Random
* *any other text* -> Log forging
