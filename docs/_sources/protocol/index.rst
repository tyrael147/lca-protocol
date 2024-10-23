.. 
   lca-protocol documentation master file, created by
   sphinx-quickstart on sun oct  6 20:18:00 2024.
   you can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. _protocol:

A protocol for programmatic LCA
===============================

This first protocol draft is strongly based and inspired by guidelines and protocols that were proposed to enhance the reproducibility of studies in other research fields (i.e., data science and agent-based modelling.). 
We leveraged on the recommendations provided by two main sources: `The Touring Way handbook <https://book.the-turing-way.org/index.html>`_  :footcite:p:`turing2021turing` and the `ODD protocol <https://www.jasss.org/23/2/7.html>`_ :footcite:p:`grimm2020odd`. 
We identified the pertinent topics of the existing protocols, and we matched them with fundamental aspects commonly addressed in recent state-of-the-art LCA practice. 
We divided the protocol in six sections: Project organization, project description, reproducible modelling, reproducible analysis, code style and linting, and licensing.
To facilitate the understanding, the following sections provide situations that \
exemplify the interactions between a ``PRACTITIONER`` who is the one conducting and reporting the study, and a ``REVIEWER``, who aims to reproduce the study.

.. image:: ../media/protocol-03.png
    :width: 97 % 
    :align: center
    :alt: Disentangling modern LCA workflows

Protocol sections and the promised benefits.

.. _touring_handbook: https://book.the-turing-way.org/index.html


.. footbibliography::



.. toctree::
   :maxdepth: 2
   :numbered: 4

   chapter_1
   chapter_2
   chapter_3
   chapter_4
   chapter_5
   chapter_6
