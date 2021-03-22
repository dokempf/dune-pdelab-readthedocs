Code Generation with Python
---------------------------

The Python programming language is increasingly popular in scientific applications.
Recently, we invested work into adding a code generation toolchain to dune-pdelab.
It allows to express the weak formulation of your PDE in a domain specific language (UFL)
and automatically generates the necessary integration kernels (aka the :code:`LocalOperator`)
from that input. This lesson explains the use of that system.
You can also :download:`download the lecture slides <../pdfs/codegeneration_slides.pdf>`.

.. youtube:: m26jHtaoeRE

The exercise sheet for this lesson can be :download:`downloaded here <../pdfs/exercise_codegeneration.pdf>`.
The material for this exercise can be found in the :code:`tutorial09` subfolder
of the :code:`dune-pdelab-tutorials` module.
Check :ref:`structure` for details on how to find the material.
