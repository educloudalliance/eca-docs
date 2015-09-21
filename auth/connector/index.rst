
Connector Service
*****************

The Auth Connector service is used for adding authentication methods for users in the system.

It should be possible for user to have multiple authentication methods in use
from the set of supported methods.
The authentication methods for users must be stored in the Auth Data service.

The Auth Connector service should be using Auth Proxy to authenticate users.

New user is invited to the system as Invitee.
The invitation happens by the Invitator.
Invitator must be existing user in the system.

