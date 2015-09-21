
Authentication interface
************************

The authentication interface provides authentication and user identification
data to other services.

There may be multiple protocol implementations.

Auth Proxy must implement Shibboleth protocol.


Shibboleth attributes
=====================

Data coming from Auth Data service should be directly visible to all
service providers as attributes.

There are two attributes:

educloud.oid
  Unique identifier for the user in Auth Data.
  The attribute is a string.

educloud.data
  Contains whole JSON document coming from the API.
  It is base64 encoded. The contents and structure of the JSON document
  is documented in Auth Data Interface documentation.


