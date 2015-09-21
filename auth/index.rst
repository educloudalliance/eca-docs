
Authentication
**************

.. toctree::

  proxy/index
  data/index
  connector/index
  source

Auth services provide other services user authentication and identification information.

The central component is the :doc:`Auth Proxy <proxy/index>` which has
the :doc:`authentication interface <proxy/interface>`.
Auth Proxy works as a proxy between services and authentication sources.
:doc:`Auth Sources <source>` have the actual user identity information and
perform the credential checks.

User attributes can be queried from the :doc:`Auth Data service <data/index>`.

