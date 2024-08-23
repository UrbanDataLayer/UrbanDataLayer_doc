.. UDL documentation master file, created by
   sphinx-quickstart on Thu Sep 28 10:56:06 2023.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


.. figure:: ../img/logo.png
    :scale: 20%
    :alt: logo

----

UDL (UrbanDataLayer) is a suite of standard data structure and pipeline for city data engineering, which processes city data from various raw data into a unified data format.  

**UDL** is featured for:

- Unified standardized formats for city data: five data layers (grid, graph, point, polygon and linestring).
- User-friendly APIs of data processing: scheme transformation, granularity alignment and feature fusion.


Installation
============

It is recommended to use **pip** for installation.
Please make sure **the latest version** is installed, as UDL may be updated frequently:

.. code-block:: bash

   pip install udlayer          # pip install
   pip install --upgrade udlayer  # update if needed

.. note:: If some error about *gdal* appears when installing, please install *geopandas* package manually (from wheel or use conda). It may be caused by the dependency of *geopandas*. Please ensure that the latest udlayer version is installed.


**Note on PyG and DGL Installation**\ :
Some conversion methods (in *utils*) depends on `torch <https://pytorch.org/>`_, `torch_geometric <https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html#>`_ and `DGL <https://www.dgl.ai/pages/start.html>`_.
To streamline the installation, UDL does **NOT** install these libraries for you.
Please install them from the above links if you need to convert the graph data into these two formats, otherwise you can ignore this note.

Quick Start
============
We provide complete sample process of “Identification of administrative boundaries” and “pm2.5 prediction” cases to help you get started with UDL in the `UDL repository <https://github.com/SJTU-CILAB/udl>`_.

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: Getting Started

   UDL Class
   UDL Transformation
   UDL Alignment
   UDL Fusion
   UDL Utilities



