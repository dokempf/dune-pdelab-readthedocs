Simulation Workflow
-------------------

This lecture describes a bunch of topics that are of relevance for understanding
Dune and to be able to do the exercises, but that do not really fit with any of
the other lectures' topics. You can :download:`download the lecture slides here <../pdfs/workflow_slides.pdf>`.

The first part talks about Dune's modular structure and the CMake-based build system
that Dune is using:

.. youtube:: pSId3V7S2Ec

The next part reiterates on one of the native strengths of Dune compared to competitors:
The availability of a variety of grid implementations with very different feature sets.
It also explains how grids are constructed using generic factory concepts.

.. youtube:: hWgAYXhCT0s

The third part briefly explains the configuration file format that is typically used in Dune.

.. youtube:: lz461yrPL6g

The last part is quite relevant for the exercises as it explains Dune's tackle
on visualization. File exports to the VTK format are shown and a hands-on session
with ParaView illustrates the intended workflow for the exercises:

.. youtube:: 7iDOni83uTQ

The exercise sheet for this lecture can be :download:`downloaded here <../pdfs/exercise_workflow.pdf>`.
The material for this exercise can be found in the :code:`workflow` subfolder
of the :code:`dune-pdelab-tutorials` module.
Check :ref:`structure` for details on how to find the material.
