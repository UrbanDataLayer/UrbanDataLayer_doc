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


UDL Alignment 
~~~~~~~~~~~~~~~~~~~

Overview
------------------

.. image:: ../img/Alignment.png
   :scale: 30%
   :align: center

API
------------------

``grid_align(gridlayer, start_lat, end_lat, start_lon, end_lon, target_lat_step, target_lon_step, mode="concat")``

| :blue:`PARAMETERS`:

- **gridlayer** (*GridLayer*) - The grid layer to be aligned
- **start_lat** (*float*) - Starting latitude
- **end_lat** (*float*) - Ending latitude
- **start_lon** (*float*) - Starting longitude
- **end_lon** (*float*) - Ending longitude
- **target_lat_step** (*float*) - The step of latitude of the new grid layer
- **target_lon_step** (*float*) - The step of longitude of the new grid layer
- **mode** (*string*) - The way of aggregation. "sum", "avg", "max", "min" or "random". Defaults to "avg".

  + "avg"
  + "sum"
  + "max"
  + "min"
  + "random"

| :blue:`RETURNS`:

- Grid UDL object

``graph_align(graphlayer, start_lat, end_lat, start_lon, end_lon, target_lat_step, target_lon_step)``

| :blue:`PARAMETERS`:

- **graphlayer** (*GraphLayer*) - The graph layer to be aligned
- **start_lat** (*float*) - Starting latitude
- **end_lat** (*float*) - Ending latitude
- **start_lon** (*float*) - Starting longitude
- **end_lon** (*float*) - Ending longitude
- **target_lat_step** (*float*) - The step of latitude of the new graph layer
- **target_lon_step** (*float*) - The step of longitude of the new graph layer

| :blue:`RETURNS`:

- Graph UDL object

