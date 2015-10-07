
Meta
****

.. toctree::

  data/index
  analytics/index

Services may have data which they want to describe to other services.
Examples of this type of data is metadata of learning materials, links between
statements in curriculum and learning material, and analytics metrics.

By having common vocabulary, the metadata, between learning materials, curriculum and
analytics metrics makes it possible to link the requirements and goals to actual user actions
and learning results. Learning material and analytics metrics are tagged with
keywords and same keywords are used inside the curriculum.

Usage data may be collected automatically by the systems.
Collection of data happens by the services, but the data must be accessible for
services which are analyzing the data. This can be the same service of course,
but it would be much better to share the data system wide.
This way all services can see how the user is moving between services in the whole system.
This data may even be open.

Each service collects and stores the data themselves and then periodically publishes
the data to central repository. Data is then queried back from central repository to
services which need it. Central repository behaves like a cache for the data and it
is stored there for only certain amount of time.

Each service collects the data and pushes it to central repository in realtime.
Central repository works as a publish/subscribe message bus and publishes the data
to all listening parties. Data is not stored in the repository.

Each service has common API which everyone else can use to query for metadata and metrics.
There would be retention policies how long the data must be accessible in the API.

The repository for all metadata and analytics metrics could be key/value store with
graph and timeseries functionalities. Meaning the data can have complex hierarchies
and values can contain value timeseries data.
The metadata repository can be updated by everyone and it keeps track who is doing what and why.

Requirements for the repository:

* must have a database which stores the data for certain period
* must have REST API to query the data (with public and open part)
* must have publish/subscribe API for realtime message passing
* must have an API to register services and then it must query periodically the data
  and publish it in the publish/subscribe API on behalf of the service

Services:

* may connect to the publish/subscribe API
* may have common API for querying metrics and register to the repository
* must either connect to the publish/subscribe API or have the common API
* must register metadata keywords



