
User data interface
*******************

The interface provides access to the contents of the database.

The data model in the database is not defined, but the interface must have following fields
and relations.

School has Groups. Role is defined per Group. User has Role in Group.

.. note::

 Example data: User "Teppo Testaaja" is "teacher" in Group "7A" and "7B" in School "17392".

Data returned from the API looks like this:

::

  {
    "username": "123abc",
    "first_name": "Teppo",
    "last_name": "Testaaja",
    "roles": [
      {
        "school": "17392",
        "role": "teacher",
        "group": "7A"
      },
      {
        "school": "17392",
        "role": "teacher",
        "group": "7B"
      }
    ]
    "attributes": [
      {
        "attribute1_id": "attribute1_data",
        "attribute2_id": "attribute2_data"
      }
    ]
  }

General fields:

username
  Unique identifier for the user.

first_name
  First, or given name.

last_name
  Last name, or surname.

Fields in the ``roles`` dict are defined as follows:

school
  Official school ID.

role
  Either ``teacher`` or ``student``.

group
  The class or group for the user.

In addition to role data custom attributes can be added at runtime.
These are installation specific and defined in the database.


Authentication to the API
=========================

Authentication to the API is based on tokens.
You should send ``Authorization: Token abcd1234`` header.

For example::

  curl -H "Authorization: Token 9c5d6df27105387b586286b06684ac2dcdbf09d3"  http://foo.example.com/api/1/user/


Attribute query
===============

The attribute query endpoint is meant to be used by the Auth Proxy to query for the attributes of single user.

The endpoint is ``/api/1/user?name=value`` which can be queried for the attributes. The result is JSON dict of data.

Query is made by GET parameters. Only one parameter is allowed. ``Not found`` is returned if:

* the parameter name is not recognized
* multiple results would be returned (only one result is allowed)
* no parameters are specified

In the query ``name`` is the parameter name used to filter users from the database.
Name of the parameter is defined when new auth sources are registered.
The list of valid filter names is available from system admins.
Name of the parameter can contain only ``a-z`` chars.
The value for the filter parameter is UTF-8 as urlencoded string.


User search query
=================

User objects can be searched by ``school``, ``group`` and ``username`` attributes.

Example query: ``/api/1/user/?school=Keskustan%20koulu&group=7A``

This returns all matches.


