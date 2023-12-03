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

``graphlayer_to_geometric(graph_data)``

| :blue:`PARAMETERS`:

- **graph_data** (*GraphLayer*) - The graph layer data to be transformed into a PyTorch Geometric data object

| :blue:`RETURNS`:

- The PyTorch Geometric data object.


``graphlayer_to_dgl(graph_data)``

| :blue:`PARAMETERS`:

- **graph_data** (*GraphLayer*) - The graph layer data to be transformed into a DGL data object

| :blue:`RETURNS`:

- The DGL data object.

   