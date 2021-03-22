Introduction
============

About Dune
----------

The Distributed and Unified Numerics Environment (DUNE) is a software framework
for the numerical solution of partial differential equations with grid-based methods.
Using generic programming techniques it strives for both: high flexibility
(efficiency of the programmer) and high performance (efficiency of the program).
DUNE provides, among other things, a large variety of local mesh refinement techniques,
a scalable parallel programming model, an ample collection of finite element methods
and efficient linear solvers.

About this Course
-----------------

The course material you are looking at has been used to teach an annual
one week long summer school at the Interdisplinary Center for
Scientific Computing at Heidelberg University for more than a decade.
With the pandemic prohibiting the traditional format, the course has been given
virtually for the first time in March 2021. With all our lectures being
recorded, we are making the material now available for self study.

.. _structure:

How to study with the Material
------------------------------

The course material is organized as :ref:`a number of lectures<lectures>`.
Each lecture consists of the following aspects:

* One or more YouTube videos with the actual lecture that describes
  theoretical *and* implementation aspects of the lecture topic.
* A PDF document explaining the lecture content in written form.
* An exercise sheet with assignments for you to reflect on the lecture content.

It is important to understand that both of the lecture (either in written
form or as an actual lecture) and the exercises are necessary
to build a profound understanding of the Dune framework. 

The exercise material assumes some familiarity with the Linux shell e.g.
switching directories with :code:`cd`. If you have never worked with Linux
before you might want to consider watching this video after
:ref:`setting up your environment<exercise_setup>`:

.. youtube :: ZmNFWNMlcdM

In order to do the exercise, it is important to understand the directory structure
of the course material. This structure results from the modular structure of the
Dune ecosystem: The :code:`dune` subdirectory contains sources of all required Dune
modules. The :code:`release-build` contains an *out-of-source build* performed by
CMake. This build mirrors the directory structure of the source tree, but only contains
generated files, build artifacts and simulation results:

::

   iwr-course-2021
   ├── dune
   │   ├── dune-common
   │   ├── dune-grid
   │   ├── ...
   │   └── dune-pdelab-tutorials
   │       ├── tutorial00
   │       │   ├── src
   │       │   ├── doc
   │       │   └── exercise
   │       │       ├── task
   │       │       ├── doc
   │       │       └── solution
   │       ├── tutorial01 ...
   |       └── ...
   ├── release-build
   |   ├── dune-common
   |   ├── dune-grid
   |   ├── ...
   |   └── dune-pdelab-tutorials
   |       ├── src_dir
   |       ├── tutorial00
   |       |   ├── src_dir
   |       │   ├── src
   |       |   |   └── src_dir
   |       │   ├── doc
   |       |   |   └── src_dir
   |       │   └── exercise
   |       |       ├── src_dir
   |       │       ├── task
   |       |       |   └── src_dir
   |       │       ├── doc
   |       |       |   └── src_dir
   |       │       └── solution
   |       |           └── src_dir
   |       ├── tutorial01 ...
   |       └── ...
   ├── release.opts
   └── ...

.. note::

   The :code:`src_dir` directories in the build directory are symbolic links
   to the corresponding source directory. This allows us to always operate directly
   in the build directory, but quickly jump to the correct source directory using :code:`cd`.

The relevant Dune module for the course material is :code:`dune-pdelab-tutorials`.
It contains a subdirectory per lecture. Each of these lecture directories has
the structure outlined for :code:`tutorial00` above:

* :code:`src` contains the C++ sources of the executable that is used in the
  lecture to illustrate the lecture topic. It is a fully functional simulation
  executable. There is typically additional configuration files that control
  the simulation in the :code:`src` directory.
* :code:`exercise/task` contains the C++ sources for the exercise. You are not
  expected to write C++ programs from scratch. Instead, your task is to modify
  the given program.
* :code:`exercises/solution` contains the full solution to the tasks. Feel free
  to consult it if you are stuck.
* :code:`doc` and :code:`exercise/doc` contain the Latex sources for the lecture.
  You do not need to build this yourself.

We have also summarized the structure of the lecture and exercise material
in this short video:

.. youtube :: 7mYEHKHhvCg

.. _exercise_setup:

Setting up the exercise environment
-----------------------------------

There is two ways of getting the code and the execution environment
for the course material: Directly or within a virtual machine. We
only describe the direct setup for recent Debian or Ubuntu systems,
where as the virtual machine setup will work on all operating systems.

If you are on an Debian (e.g. version 10) or Ubuntu (e.g. 20.04 LTS)
system, you should open a terminal and execute the following sequence
of commands will download and build the course material on your computer.

.. code:: bash

   sudo apt install git cmake build-essential paraview gmsh libsuitesparse-dev libsuperlu-dev openmpi-bin libopenmpi-dev python3-dev python3-pip pkg-config
   git clone --recursive https://gitlab.dune-project.org/dune-course/iwr-course-2021.git
   cd iwr-course-2021
   ./install.sh

.. note:: Building the course material can take up to an hour. Be patient and do not close the terminal.

If you are running a different operating system, you can instead work in
a virtual machine. In order to do so you need to:

* Install VirtualBox version 6.1 from https://www.virtualbox.org
* Download our VM image from here: https://heibox.uni-heidelberg.de/f/be208766b89f4d2188cb/?dl=1
* Add the VM to VirtualBox and start it.
* Log in to the Debian 10 guest system with the user *dune* and the password *course*

The following video runs you through the process of getting the
virtual machine to run. If you have never worked with virtual machines
before, you can also watch this video that runs you through the process:

.. youtube:: IsoC5mDyHzE
