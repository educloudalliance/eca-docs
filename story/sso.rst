
Single sign-on
**************

* It must be possible for user to move between services effortlessly
* User should have multiple authentication levels based on
  the confidence of the authentication
* User should be authenticated only once per authentication level
* User can be asked to give credentials again when the action requires
  string confidence level of user authentication

All users of the system, in all services, should be able to move between services
freely without need to remember and enter passwords or other credentials multiple times.

As the user experience must be coherent between services user should have
a feeling she is inside one system.


As the Auth Data service tries to model the real situation where one user can be
teacher and student in different shools this has to be here.
It is also possible to decide that only one role object per user
is acceptable when the data is imported to the database.
