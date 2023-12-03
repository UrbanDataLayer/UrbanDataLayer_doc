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

UDL Class 
~~~~~~~~~~~~~~~

Overview
------------------
.. image:: ../img/Class.png
   :scale: 30%
   :align: center

Grid
------------------
.. code-block:: python

    class GridLayer(name, start_lat, end_lat, step_lat, start_lon, end_lon, 
        step_lon, year=None)

| :blue:`PARAMETERS`:

- **name** (*string*) - Name of the layer
- **start_lat** (*float*) - Starting latitude
- **end_lat** (*float*) - Ending latitude
- **step_lat** (*float*) - The difference of latitude between cells
- **start_lon** (*float*) - Starting lontitude
- **end_lon** (*float*) - Ending lontitude
- **step_lon** (*float*) - The difference of lontitude between cells
- **year** (*int*) - The year of dataset


| :red:`construct_grid` (data)

PARAMETERS:

- **grid_data** (*GridLayer*) - The grid data in the form of GridLayer

| :red:`get_value` (lat, lon):

PARAMETERS:

- **lat** (*float*) - Latitude to be queried
- **lon** (*float*) - Longitude to be queried

RETURNS:

- **value** (*float*) - Value at the queried location

| :red:`get_value_by_grid` (lat, lon):

PARAMETERS:

- **lat** (*numpy.array*) - Latitudes to be queried in an array of one dimension
- **lon** (*numpy.array*) - Longitudes to be queried in an array of one dimension

RETURNS:

- **value** (*numpy.array*) - Values at the queried locations in an array of one dimension

Graph
------------------
.. code-block:: python

    class GraphLayer(name, year=None, directed=False)

.. note:: The methods of `NetworkX`_ are also available for the GraphLayer's data object (GraphLayer.data).

.. _NetworkX: https://networkx.org/

| :blue:`PARAMETERS`:

- **name** (*string*) - Name of the layer
- **year** (*int*) - The year of the dataset
- **directed** (*bool*) - Whether the graph is directed

| :red:`construct_node` (node_label, latitude, longitude, node_attribute=None)

PARAMETERS:

- **node_label** (*list*) -  The list of the name of node
- **latitude** (*list[float]*) - The list of the latitude of node
- **longitude** (*list[float]*) - The list of the longitude of node
- **node_attribute** (*list*) - The list of the attribute (whose name is layer's name) values of node (optional)

RETURNS:

- **node_list** (*list[tuple]*) - The list of the tuple which can be used to construct the graph nodes

| :red:`construct_edge` (source: list, target: list, edge_attribute=None, edge_weight=None)

PARAMETERS:

- **source** (*list*) - The list of the source nodes of each edge
- **target** (*list*) - The list of the target nodes of each edge
- **edge_attribute** (*string*) - The attribute name of edge (optional)
- **edge_weight** (*list[float]*) - The list of the weight of edge (optional)

RETURNS:

- **edge_list** (*list[tuple]*) - The list of the tuple which can be used to construct the graph egdes

| :red:`construct_graph` (node_label, latitude, longitude, source: list, target: list, node_attribute=None, edge_attribute=None, edge_weight=None)

PARAMETERS:

- **node_label** (*list*) -  The list of the name of node
- **latitude** (*list[float]*) - The list of the latitude of node
- **longitude** (*list[float]*) - The list of the longitude of node
- **source** (*list*) - The list of the source nodes of each edge
- **target** (*list*) - The list of the target nodes of each edge
- **node_attribute** (*list[string]*) - The list of the attribute (whose name is layer's name) values of node (optional)
- **edge_attribute** (*string*) - The attribute name of edge (optional)
- **edge_weight** (*list[float]*) - The list of the weight of edge (optional)

RETURNS:

- **graph** (*GraphLayer*) - The graph data in the form of GraphLayer


Point
------------------
.. code-block:: python

    class PointLayer(name, year=None, column_list=None)

.. note:: The methods of `pandas.DataFrame`_ are also available for the PointLayer's data object (PointLayer.data).

.. _pandas.DataFrame: https://pandas.pydata.org/docs/reference/frame.html

| :blue:`PARAMETERS`:

- **name** (*string*) - Name of the layer
- **year** (*int*) - The year of the dataset
- **column_list** (*list[string]*) - The list of the attribute names of the point data

| :red:`add_points` (data_df)

PARAMETERS:

- **data_df** (*pandas.DataFrame*) - The dataframe of the point data

| :red:`delete_point` (lat, lon)

PARAMETERS:

- **lat** (*float*) - Latitude of the point to be deleted
- **lon** (*float*) - Longitude of the point to be deleted

| :red:`get_value` (lat, lon, feature_name=None)

PARAMETERS:

- **lat** (*float*) - Latitude of the point to be queried
- **lon** (*float*) - Longitude of the point to be queried
- **feature_name** (*list[string]*) - The attribute name of the point data to be queried (optional)

RETURNS:

- **value** (*numpy.array*) - Value at the queried location

| :red:`get_value_by_range` (start_lat, end_lat, start_lon, end_lon, feature_name=None)

PARAMETERS:

- **start_lat** (*float*) - Starting latitude of the range to be queried
- **end_lat** (*float*) - Ending latitude of the range to be queried
- **start_lon** (*float*) - Starting longitude of the range to be queried
- **end_lon** (*float*) - Ending longitude of the range to be queried
- **feature_name** (*list[string]*) - The attribute name of the point data to be queried (optional)

RETURNS:

- **value** (*numpy.array*) - Value at the queried location

| :red:`to_gpd` ()

RETURNS:

- **data** (*geopandas.GeoDataFrame*) - The geopandas dataframe of the point data

Linestring
------------------
.. code-block:: python

    class LinestringLayer(name, file=None, year=None, column_list=[])

.. note:: The methods of `geopandas.GeoDataFrame`_ are also available for the LinestringLayer's data object (LinestringLayer.data).

.. _geopandas.GeoDataFrame: https://geopandas.org/en/stable/docs/reference/geodataframe.html

| :blue:`PARAMETERS`:

- **name** (*string*) - Name of the layer
- **file** (*string*) - The path of the file (the file can be read by geopandas, e.g. shapefile and GeoJson) which contains the linestring data. If the file is not given, the linestring data will be empty.
- **year** (*int*) - The year of the dataset
- **column_list** (*list[string]*) - The list of the attribute names of the linestring data

| :red:`add_polygons` (data_gdf)

PARAMETERS:

- **data_gdf** (*geopandas.GeoDataFrame*) - The geopandas dataframe of the linestring data to be added


Polygon
------------------
.. code-block:: python

    class PolygonLayer(name, file=None, year=None, column_list=[])

.. note:: The methods of `geopandas.GeoDataFrame`_ are also available for the PolygonLayer's data object (PolygonLayer.data).

.. _geopandas.GeoDataFrame: https://geopandas.org/en/stable/docs/reference/geodataframe.html

| :blue:`PARAMETERS`:

- **name** (*string*) - Name of the layer
- **file** (*string*) - The path of the file (the file can be read by geopandas, e.g. shapefile and GeoJson) which contains the polygon data. If the file is not given, the polygon data will be empty.
- **year** (*int*) - The year of the dataset
- **column_list** (*list[string]*) - The list of the attribute names of the polygon data

| :red:`add_polygons` (data_gdf)

PARAMETERS:

- **data_gdf** (*geopandas.GeoDataFrame*) - The geopandas dataframe of the polygon data to be added
