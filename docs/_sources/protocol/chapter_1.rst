Project organization
====================

This section describes the characteristics that should rule project's organization.
Three subsections are proposed with the objective of being the initial scaffold of any \
Life Cycle-ish project.


Folder structure
----------------

The folders should be organized in such a way that: 
    
    * The root folder is exclusively reserved for subfolders or files containing \
      environmental variables, configuration files, or temporal files. 
    * The risk of exposing undesired data is minimized.
    * Each folder contains files that share the same functionality or purpose.
    * The directory tree has the minimum number of leafs so folders do not repeat purpose. 
    * A ``PRACTITIONER`` should not have to modify the folder structure during the iterative development phase or 
      \while conducting collaborative work.
    * A file should always belong to just one folder without ambiguity.
    * The project SHOULD be self contained, meaning that any code SHOULD not call parent folders [#f1]_




We propose a folder structure, based and inspired on recommendations provided by \
`The Turing Way <turing-way-repo_>`_, `CCS-Amsterdam`_, `pyscaffold`_, \
and a `cookiecutter-template`_ template.


.. _turing-way-repo: https://github.com/the-turing-way/reproducible-project-template

.. _CCS-Amsterdam: https://github.com/ccs-amsterdam/compendium

.. _pyscaffold: https://github.com/pyscaffold/pyscaffoldext-dsproject

.. _cookiecutter-template: https://github.com/drivendataorg/cookiecutter-data-science


The folder structure should resemble this:


.. code-block:: console

   {{project_name}}
   ├── .env    <- File containing definitions for environmental variables
   ├── .bw2projects    <- Folder used to store required in packages like brightway
   ├── data
   │   ├── private     <- Everything here is ignored in .gitignore
   │   │   ├── processed
   │   │   │   └── README.md
   │   │   ├── raw
   │   │   │   └── README.md
   │   │   └── README.md
   │   ├── processed   <- Ultimate/canonical form of the data before being ingested into a model.
   │   │   └── README.md
   │   └── raw   <- Pristine and unmodified data resources.
   │       └── README.md
   ├── environment.yaml  <- To build environment when conda is installed.
   ├── requirements.txt  <- To intall dependencies using pypi.
   ├── models  <- Contains serialized, ready-to-use models.
   │   └── README.md
   ├── README.md <- General description of the project
   └── src <- Contains pure code
       ├── analysis <- Scripts and notebooks used to analyse results.
       │   └── README.md
       ├── processing  <- Routines used to process raw data.
       │   └── README.md
       └── models  <- Scripts and notebooks containing the code that generates models.
           └── README.md



Version control
---------------

As exhaustively explained in :footcite:t:`turing2021turing`, version control is a practice \
that aims to record all the changes made to files inside a folder.
In an LCA project, keeping track of these changes is fundamental since most of the modelling stages constantly consume (e.g., inventories) and produce (e.g., life cycle impacts) data files.
In a collaborative environment, maintaining a record of versions permits the ``PRACTIONER`` to have a control of the inventories or parameters that are being feed to the LCA model.
Similarly, this practice can also guarantee the traceability of the inventories or \
results that come from the LCA model and that will be fed into other computational pipelines. 

Despite of the existence of different tools that fulfill this purpose, the protocol proposes `git <https://git-scm.com/>`_ as the most convenient \
version control system since it is free and open-source, it is compatible with multiple Operating Systems, and it has been widely adopted among multiple disciplines [#f2]_.

In the protocol, `git` technology MUST be adopted to ensure that:

    * The ``PRACTITIONER`` can use it to keep track of the history of changes of all \
      the files in the project.
    * Many ``PRACTITIONERs`` can work simultaneously or with different versions of \
      the same project.
    * The ``REVIEWER`` is capable of exploring the progress and versions of the project. 
    * The ``PRACTITIONER`` can determine folders or files are public or private according to the project needs. 
    * The ``PRACTITIONER`` can identify the author of a specific change.
    * Both the ``REVIEWER`` and the ``PRACTITIONER`` can download or upload the project\
      repository to a remote hosting website (e.g., github, gitlab or bitbucket). 


.. note::
    
    Section `Folder Structure`_ has been elaborated having ``git`` in mind.
    In this sense, ``git`` can be used to prevent private files to be exposed by including \
    them into a configuration file named ``.gitignore``.
    For instance, the folder structure presented in the previous section should contain \
    a ``.gitignore`` file like this:  

    .. code-block:: console

        $cat .gitignore
        .bw2projects
        data/private/*
        .env


Naming conventions
------------------

TODO: This is exhaustively clarified in `<https://book.the-turing-way.org/project-design/filenaming>`_, verify if adaptation is needed.

.. rubric:: Footnotes

.. footbibliography::

.. [#f1] LCA packages like `brightway` MAY require to store data on disk. This means \
    that the ``PRACTITIONER`` MUST ensure that any `brightway` `environmental variable <https://docs.brightway.dev/en/latest/content/faq/data_management.html#how-do-i-change-my-data-directory>`_ refers to a folder located inside the project.
.. [#f2] The protocol is not focused on providing guidance on the use of ``git``. Multiple tutorials can be found `here <https://learn.microsoft.com/en-us/training/modules/collaborate-with-git/>`_ and `here <https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners>`_. 

