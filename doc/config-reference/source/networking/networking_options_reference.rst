================================
Networking configuration options
================================

The options and descriptions listed in this introduction are auto
generated from the code in the Networking service project, which
provides software-defined networking between VMs run in Compute. The
list contains common options, while the subsections list the options
for the various networking plug-ins.

.. include:: ../tables/neutron-common.rst

Networking plug-ins
~~~~~~~~~~~~~~~~~~~

OpenStack Networking introduces the concept of a
plug-in, which is a back-end implementation of the
OpenStack Networking API. A plug-in can use a
variety of technologies to implement the logical API
requests. Some OpenStack Networking plug-ins might
use basic Linux VLANs and IP tables, while others
might use more advanced technologies, such as
L2-in-L3 tunneling or OpenFlow. These sections
detail the configuration options for the various
plug-ins.

CISCO configuration options
---------------------------

.. include:: ../tables/neutron-cisco.rst

CloudBase Hyper-V Agent configuration options
---------------------------------------------

.. include:: ../tables/neutron-hyperv_agent.rst

Layer 2 Gateway configuration options
-------------------------------------

.. include:: ../tables/neutron-l2_agent.rst

Linux bridge Agent configuration options
----------------------------------------

.. include:: ../tables/neutron-linuxbridge_agent.rst

MacVTap Agent configuration options
----------------------------------------

.. include:: ../tables/neutron-macvtap_agent.rst

NEC configuration options
-------------------------

.. include:: ../tables/neutron-nec.rst

Open vSwitch Agent configuration options
----------------------------------------

.. include:: ../tables/neutron-openvswitch_agent.rst

IPv6 Prefix Delegation configuration options
--------------------------------------------

.. include:: ../tables/neutron-pd_linux_agent.rst

Modular Layer 2 (ml2) configuration options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Modular Layer 2 (ml2) plug-in has two components:
network types and mechanisms. You can configure these
components separately. The ml2 plugin also allows administrators to
perform a partial specification, where some options are specified
explicitly in the configuration, and the remainder is allowed to be chosen
automatically by the Compute service.

This section describes the available configuration options.

.. note::
   OpenFlow Agent (ofagent) Mechanism driver has been removed
   as of Newton.

.. include:: ../tables/neutron-ml2.rst

Modular Layer 2 (ml2) Flat Type configuration options
-----------------------------------------------------

.. include:: ../tables/neutron-ml2_flat.rst

Modular Layer 2 (ml2) GRE Type configuration options
----------------------------------------------------

.. include:: ../tables/neutron-ml2_gre.rst

Modular Layer 2 (ml2) VLAN Type configuration options
-----------------------------------------------------

.. include:: ../tables/neutron-ml2_vlan.rst

Modular Layer 2 (ml2) VXLAN Type configuration options
------------------------------------------------------

.. include:: ../tables/neutron-ml2_vxlan.rst

Modular Layer 2 (ml2) Geneve Mechanism configuration options
-------------------------------------------------------------

.. include:: ../tables/neutron-ml2_geneve.rst

Modular Layer 2 (ml2) L2 Population Mechanism configuration options
-------------------------------------------------------------------

.. include:: ../tables/neutron-ml2_l2pop.rst

Modular Layer 2 (ml2) SR-IOV Mechanism configuration options
------------------------------------------------------------

.. include:: ../tables/neutron-ml2_sriov.rst

Configure the Oslo RPC messaging system
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

OpenStack projects use an open standard for messaging middleware known
as AMQP. This messaging middleware enables the OpenStack services that
run on multiple servers to talk to each other. OpenStack Oslo RPC
supports two implementations of AMQP: RabbitMQ and ZeroMQ.

Configure RabbitMQ
------------------

OpenStack Oslo RPC uses RabbitMQ by default. Use these options to
configure the RabbitMQ message system. The ``rpc_backend`` option is
optional as long as RabbitMQ is the default messaging system. However,
if it is included the configuration, you must set it to
``neutron.openstack.common.rpc.impl_kombu``:

.. code-block:: ini

   rpc_backend = neutron.openstack.common.rpc.impl_kombu

Use these options to configure the
RabbitMQ messaging system. You can
configure messaging communication for different installation
scenarios, tune retries for RabbitMQ, and define the size of the
RPC thread pool. To monitor notifications through RabbitMQ, you
must set the ``notification_driver`` option to
``neutron.openstack.common.notifier.rpc_notifier`` in the
``neutron.conf`` file.

.. include:: ../tables/neutron-rabbitmq.rst

Configure ZeroMQ
----------------

Use these options to configure the ZeroMQ messaging system for
OpenStack Oslo RPC. ZeroMQ is not the default messaging system,
so you must enable it by setting the ``rpc_backend`` option in
the ``neutron.conf`` file.

.. include:: ../tables/neutron-zeromq.rst

Configure messaging
-------------------

Use these common options to configure the RabbitMQ and ZeroMq
messaging drivers in the ``neutron.conf`` file.

.. include:: ../tables/neutron-rpc.rst
.. include:: ../tables/neutron-redis.rst
.. include:: ../tables/neutron-amqp.rst

Agent
~~~~~

Use the following options to alter agent-related settings.

.. include:: ../tables/neutron-agent.rst

API
~~~

Use the following options to alter API-related settings.

.. include:: ../tables/neutron-api.rst

Token authentication
~~~~~~~~~~~~~~~~~~~~

Use the following options to alter token authentication settings.

.. include:: ../tables/neutron-auth_token.rst


Compute
~~~~~~~

Use the following options to alter Compute-related settings.

.. include:: ../tables/neutron-compute.rst

CORS
~~~~

Use the following options to alter CORS-related settings.

.. include:: ../tables/neutron-cors.rst

Database
~~~~~~~~

Use the following options to alter Database-related settings.

.. include:: ../tables/neutron-database.rst

DHCP agent
~~~~~~~~~~

Use the following options to alter Database-related settings.

.. include:: ../tables/neutron-dhcp_agent.rst

Distributed virtual router
~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options to alter DVR-related settings.

.. include:: ../tables/neutron-dvr.rst


Firewall-as-a-Service driver
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options in the ``fwaas_driver.ini``
file for the FWaaS driver.

.. include:: ../tables/neutron-fwaas.rst
.. include:: ../tables/neutron-fwaas_ngfw.rst
.. include:: ../tables/neutron-fwaas_varmour.rst

Load-Balancer-as-a-Service configuration options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options in the ``neutron_lbaas.conf`` file for the
LBaaS agent.

.. include:: ../tables/neutron-lbaas.rst

Use the following options in the ``lbaas_agent.ini`` file for the
LBaaS agent.

.. include:: ../tables/neutron-lbaas_agent.rst

Use the following options in the ``services_lbaas.conf`` file for the
LBaaS agent.

.. include:: ../tables/neutron-lbaas_services.rst


VPN-as-a-Service configuration options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options in the ``vpnaas_agent.ini`` file for the
VPNaaS agent.

.. include:: ../tables/neutron-vpnaas.rst
.. include:: ../tables/neutron-vpnaas_ipsec.rst
.. include:: ../tables/neutron-vpnaas_openswan.rst
.. include:: ../tables/neutron-vpnaas_strongswan.rst

.. note::

   ``strongSwan`` and ``Openswan`` cannot both be installed and enabled at the
   same time. The ``vpn_device_driver`` configuration option in the
   ``vpnaas_agent.ini`` file is an option that lists the VPN device
   drivers that the Networking service will use. You must choose either
   ``strongSwan`` or ``Openswan`` as part of the list.

.. important::

   Ensure that your ``strongSwan`` version is 5 or newer.

To declare either one in the ``vpn_device_driver``:

.. code-block:: ini

   #Openswan
   vpn_device_driver = ['neutron_vpnaas.services.vpn.device_drivers.ipsec.OpenSwanDriver']

   #strongSwan
   vpn_device_driver = ['neutron.services.vpn.device_drivers.strongswan_ipsec.StrongSwanDriver']

IPv6 router advertisement
~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options to alter IPv6 RA settings.

.. include:: ../tables/neutron-ipv6_ra.rst

L3 agent
~~~~~~~~

Use the following options in the ``l3_agent.ini`` file for the L3
agent.

.. include:: ../tables/neutron-l3_agent.rst

Load Balancing service (octavia)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Use the following options to configure the octavia service:

.. include:: ../tables/octavia-api.rst
.. include:: ../tables/octavia-auth_token.rst
.. include:: ../tables/octavia-cache.rst
.. include:: ../tables/octavia-common.rst
.. include:: ../tables/octavia-cors.rst
.. include:: ../tables/octavia-database.rst
.. include:: ../tables/octavia-logging.rst
.. include:: ../tables/octavia-rabbitmq.rst
.. include:: ../tables/octavia-redis.rst
.. include:: ../tables/octavia-rpc.rst
.. include:: ../tables/octavia-zeromq.rst

Logging
~~~~~~~

Use the following options to alter logging settings.

.. include:: ../tables/neutron-logging.rst

Metadata Agent
~~~~~~~~~~~~~~

Use the following options in the
``metadata_agent.ini`` file for the Metadata agent.

.. include:: ../tables/neutron-metadata.rst

.. note::

   Previously, the neutron metadata agent connected to a neutron
   server via REST API using a neutron client. This is ineffective
   because keystone is then fully involved into the authentication
   process and gets overloaded.

   The neutron metadata agent has been reworked to use RPC by default
   to connect to a server since Kilo release. This is a typical way of
   interacting between neutron server and its agents. If neutron
   server does not support metadata RPC then neutron client will be
   used.

.. warning::

   Do not run the ``neutron-ns-metadata-proxy`` proxy namespace as
   root on a node with the L3 agent running. In OpenStack Kilo and
   newer, you can change the permissions of
   ``neutron-ns-metadata-proxy`` after the proxy installation using
   the ``metadata_proxy_user`` and ``metadata_proxy_group`` options.

Metering Agent
~~~~~~~~~~~~~~

Use the following options in the ``metering_agent.ini`` file for the
Metering agent.

.. include:: ../tables/neutron-metering_agent.rst

Nova
~~~~

Use the following options in the
``neutron.conf`` file to change nova-related settings.

.. include:: ../tables/neutron-nova.rst

Policy
~~~~~~

Use the following options in the ``neutron.conf`` file to change
policy settings.

.. include:: ../tables/neutron-policy.rst

Quotas
~~~~~~

Use the following options in the ``neutron.conf`` file for the quota
system.

.. include:: ../tables/neutron-quotas.rst

Scheduler
~~~~~~~~~

Use the following options in the ``neutron.conf`` file to change
scheduler settings.

.. include:: ../tables/neutron-scheduler.rst

Security Groups
~~~~~~~~~~~~~~~

Use the following options in the configuration file for your driver to
change security group settings.

.. include:: ../tables/neutron-securitygroups.rst

.. note::

   Now Networking uses iptables to achieve security group functions.
   In L2 agent with ``enable_ipset`` option enabled, it makes use of
   IPset to improve security group's performance, as it represents a
   hash set which is insensitive to the number of elements.

   When a port is created, L2 agent will add an additional IPset chain
   to it's iptables chain, if the security group that this port
   belongs to has rules between other security group, the member of
   that security group will be added to the ipset chain.

   If a member of a security group is changed, it used to reload
   iptables rules which is expensive. However, when IPset option is
   enabled on L2 agent, it does not need to reload iptables if only
   members of security group were changed, it should just update an
   IPset.

.. note::

   A single default security group has been introduced in order to
   avoid race conditions when creating a tenant's default security
   group. The race conditions are caused by the uniqueness check of a
   new security group name. A table ``default_security_group``
   implements such a group. It has ``tenant_id`` field as a primary
   key and ``security_group_id``, which is an identifier of a default
   security group. The migration that introduces this table has a
   sanity check that verifies if a default security group is not
   duplicated in any tenant.

Misc
~~~~

.. include:: ../tables/neutron-bgp.rst
.. include:: ../tables/neutron-qos.rst
