
Data Service
************

.. toctree::

  interface


The Auth Data service is an abstraction of actual data store, or multiple datastores,
which contain user identity and role information.

The Auth Data service may not have visible UI.
The Auth Data service must have an interface which can be used to query the contents of the database.

The Auth Data service may have other interfaces which are used to update the database.
These interfaces may be either push or pull.
Database update may also be done manually in batches.


