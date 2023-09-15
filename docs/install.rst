.. _installation:

============
Installation
============

You can easily install small-text using pip or conda:

**Using Pip**

.. code-block:: console

    pip install small-text

**Using Conda**

.. code-block:: console

    conda install small-text

This installs a minimal setup **without** any integrations. By installing the :ref:`integrations<install:Optional Integrations>`
you can enable larger scopes of gpu-based functionality.
Further :ref:`optional dependencies<install:Optional Dependencies>`, i.e. dependencies which are only needed for one to a few strategies
and are not installed by default (to avoid bloated dependencies), might be required.

.. _installation-optional-dependencies:

----

Optional Integrations
=====================

The small-text library is designed to be usable in combination with as many classifiers/classification libraries as possible.
Whenever possible, we try to keep most dependencies optional to avoid dependency bloat.
Dependending on the classifier of your choice, you might need additional python libraries.

.. note:: The `Pytorch` and `Transformers` Integrations are best used with a CUDA-capable GPU.
          You need CUDA version |CUDA_VERSION| or newer, and your GPU must also support that specific version.


.. _installation-pytorch:

Pytorch Integration
-------------------

**Using Pip**

To enable the Pytorch Integration, install the library with the `pytorch` extra:

.. code-block:: console

    pip install small-text[pytorch]

**Using Conda**

.. code-block:: console

    conda install small-text "torch>=1.6.0"

.. _installation-transformers:

Transformers Integration
------------------------

**Using Pip**

To enable the Transformers Integration, install the library with the `transformers` extra:

.. code-block:: console

    pip install small-text[transformers]

**Using Conda**

.. code-block:: console

    conda install small-text "torch>=1.6.0" "transformers>=4.0.0"

The Transformers Integration also requires Pytorch, so installing this automatically
entails an installation of the Pytorch Integration.

----

Optional Dependencies
=====================

We keep certain python dependencies optional when they are either needed
for very specific functionality (e.g., certain query strategis or stopping criteria) or are pure convenience functions.

An overview of such dependencies is provided in the table below:

+-------------------------+------------------------------------------------------------------------------------------------+
| Dependency              | Required by                                                                                    |
+=========================+================================================================================================+
| `gensim>=4.0.0`_        | Code Examples, Approval Tests, Integration Tests                                               |
+-------------------------+------------------------------------------------------------------------------------------------+
| `hnswlib`_              | :py:class:`~small_text.query_strategies.strategies.SEALS`                                      |
+-------------------------+------------------------------------------------------------------------------------------------+
| `scikit-learn>=1.3.0`_  | :py:class:`~small_text.utils.clustering.init_kmeans_plusplus_safe()`                           |
+-------------------------+------------------------------------------------------------------------------------------------+
| `setfit`_               | :py:class:`~small_text.integrations.transformers.classifiers.setfit.SetFitClassification`      |
+-------------------------+------------------------------------------------------------------------------------------------+

.. _`gensim>=4.0.0`: https://pypi.org/project/gensim/

.. _hnswlib: https://pypi.org/project/hnswlib/

.. _`scikit-learn>=1.3.0`: https://pypi.org/project/scikit-learn/

.. _setfit: https://github.com/huggingface/setfit
