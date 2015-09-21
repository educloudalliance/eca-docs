
Authentication interface
************************

The authentication interface provides authentication and user identification
data to other services.

There may be multiple protocol implementations.

Auth Proxy must implement Shibboleth protocol.

Attributes
==========

Authentication data should contain only the info to identify person.
For example license info is not included in authentication parameters,
but with the unique id, license info could be asked from another service.

Following attributes must be available always:

Unique identifier
  Unique identifies on national level. For example in Finland ‘Oppijanumero’. https://confluence.csc.fi/download/attachments/8127300/Oppijanumero+ja+OID.pdf

Authentication confidence level
  How strong the Auth Proxy thinks the authentication confidence level is.

Following attributes should be available always:

Name
  First name or given name, and Surname.

Contact information
  Email, phone number.

Role
  Role in school. Teacher, student, pupil, principal for example.

School
  The school identified with school’s national id

Municipality
  Code to identify municipality. Municipality list in Finland: http://www02.oph.fi/asiakkaat/rahoitus/perus01k/forms/kuntalista_help1.html


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


