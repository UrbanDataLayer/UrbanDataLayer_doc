.. role:: red
    :class: red

.. role:: blue
    :class: blue

.. role:: green
    :class: green

.. raw:: html

    <style>

    .red {
        color:#A42115;
    }
    .blue {
        color:#3659D7;
    }
    .green {
        color:green;
    }

    </style>


UDL Utilities 
~~~~~~~~~~~~~~~~~~~

``get_coord_type(filedir, row, col)``

| :blue:`PARAMETERS`:

- **filedir** (*str*) - The directory of the TIF file waiting to be transformed into a grid layer.
- **row** (*int*) - The row number of the TIF file.
- **col** (*int*) - The column number of the TIF file.

| :blue:`RETURNS`:

- coordinate (*tuple*): The coordinate of the positions at the given row and column.

.. note:: To get the type of the coordinate, run `get_coord_type(filedir, 0, 0)` to get the coordinate of the top left corner.
    If the tuple is (latitute, longitude), then the parameter "coord_type" is "latlon". Otherwise, the parameter "coord_type" is "lonlat".

.. warning:: Adding GDAL as a dependency to the package or using "pip install gdal" may fail. It is recommended to install GDAL using the following command: "conda install -c conda-forge gdal".

``graphlayer_to_torch(graph_data)``

| :blue:`PARAMETERS`:

- **graph_data** (*GraphLayer*) - The graph layer data to be transformed into a PyTorch Geometric data object
- **node_attr** (*list[string]*) - The list of converted node attributes
- **edge_attr** (*list[string]*) - The list of converted edge attributes

| :blue:`RETURNS`:

- The PyTorch Geometric data object.


``graphlayer_to_dgl(graph_data)``

| :blue:`PARAMETERS`:

- **graph_data** (*GraphLayer*) - The graph layer data to be transformed into a DGL data object
- **node_attr** (*list[string]*) - The list of converted node attributes
- **edge_attr** (*list[string]*) - The list of converted edge attributes

| :blue:`RETURNS`:

- The DGL data object.

``graphlayer_to_nx(graph_data)``

| :blue:`PARAMETERS`:

- **graph_data** (*GraphLayer*) - The graph layer data to be transformed into a NetworkX data object

| :blue:`RETURNS`:

- The NetworkX data object.

``graphlayer_to_igraph(graph_data)``

   