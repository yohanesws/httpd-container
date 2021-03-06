Apache HTTP Server Docker Images
================================

This repository contains Dockerfiles for Apache HTTP Server images for OpenShift and general usage.
Users can choose between RHEL and CentOS based images.


Versions
---------------
Apache HTTPD versions currently provided are:
* [httpd-2.4](2.4)

RHEL versions currently supported are:
* RHEL 7

CentOS versions currently supported are:
* CentOS 7


Installation
----------------------
Choose either the CentOS7 or RHEL7 based image:

*  **RHEL7 based image**

    This image is available in Red Hat Container Registry. To download it run:

    ```
    $ docker pull registry.access.redhat.com/rhscl/httpd-24-rhel7
    ```

    To build a RHEL7 based Apache HTTP Server image, you need to run Docker build on a properly
    subscribed RHEL machine.

    ```
    $ git clone --recursive https://github.com/sclorg/httpd-container.git
    $ cd httpd-container
    $ make build TARGET=rhel7 VERSION=2.4
    ```

*  **CentOS7 based image**

    This image is available on DockerHub. To download it run:

    ```
    $ docker pull centos/httpd-24-centos7
    ```

    To build a CentOS based Apache HTTP Server image from scratch run:

    ```
    $ git clone --recursive https://github.com/sclorg/httpd-container.git
    $ cd httpd-container
    $ make build TARGET=centos7 VERSION=2.4
    ```

For using other versions of Apache HTTP Server, just replace the `2.4` value by particular version
in the commands above.

**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of Apache HTTP Server, which must be specified in  `VERSIONS` variable.
This variable must be set to a list with possible versions (subdirectories).**


Usage
---------------------------------

For information about usage of Dockerfile for Apache HTTP Server 2.4,
see [usage documentation](2.4).


Test
---------------------------------

This repository also provides a test framework, which checks basic functionality
of the Apache HTTP Server image.

Users can choose between testing Apache HTTP Server based on a RHEL or CentOS image.

*  **RHEL based image**

    To test a RHEL7 based Apache HTTP Server image, you need to run the test on a properly
    subscribed RHEL machine.

    ```
    $ cd httpd-container
    $ make test TARGET=rhel7 VERSION=2.4
    ```

*  **CentOS based image**

    ```
    $ cd httpd-container
    $ make test TARGET=centos7 VERSION=2.4
    ```

For using other versions of Apache HTTP Server, just replace the `2.4` value by particular version
in the commands above.

**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of Apache HTTP Server, which must be specified in  `VERSIONS` variable.
This variable must be set to a list with possible versions (subdirectories).**

