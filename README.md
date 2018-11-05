Microsoft Azure director importer module for Icinga Web 2
=========================================================

This is a simple Azure module for Icinga Web 2. Currently implented is an
Import Source provider for [Icinga Director](https://github.com/Icinga/icingaweb2-module-director).
It can import either virtual machines, load blanacers or application gateways
from all, one or multiple resource groups availsable to the given api
credentials.

This data can be used to be deployed immediately as new (virtual) hosts to your
[Icinga](https://www.icinga.org/) monitoring system.


Documentation
-------------

### Basics
 * [Installation](doc/01-Installation.md)
 * [ImportSource](doc/02-ImportSource.md)
 * [Fields queried](doc/05-FieldsQueried.md)
 * [Troubleshooting](doc/99-Troubleshooting.md)

Furthermore, there is a [ChangeLog](ChangeLog) file.


Implemented features
--------------------

Currently, we have some resources implemented in this importer module:

* Virtual machines
* Disks for virtual machines
* Interfaces for virtual machines
* Load balancers
* Application Gateways
* Microsoft.DBforPostgreSQL servers (SAAS)
* Express route circuits
* Resource Groups
* Subscriptions

While the first five are tested and should be working smoothly, the PostgreSQL
and Express route circuit object types are considered untested.

This list will be enhanced with any release step by step. If you miss something,
we would appreciate an open issue on this here on GitHub. The same applies for
missing fields on the import types.

![Query types](/doc/screenshot/azure_object_types.png)

The importer can deal with multiple resource groups in a subscription. You can
either query any of these or select one or more while configuring it.

Troubleshooting should be easy as the **Azure Importer** does send log
information through the IcingaWeb2 logging pipeline. Just have your IcingaWeb2
logging configured and make shure that you get INFO level messages as well. 


Dependencies
------------

This module has no dependencies on any SDK or other external files except
for the php-curl extension, which must be enabled. 


Credits
-------

This module makes use of

https://github.com/tcdent/php-restclient

published under the MIT license. The REST client code was slightly modified to
fit into namespaces and uses valid exception classes suitable for IcingaWeb2

The code was inspired by the [Icinga Web 2 module for vSphere](https://github.com/Icinga/icingaweb2-module-vsphere)
as well as by the [AWS module for Icinga Web 2](https://github.com/Icinga/icingaweb2-module-aws).

