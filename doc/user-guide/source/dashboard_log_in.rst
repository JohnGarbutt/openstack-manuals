=======================
Log in to the dashboard
=======================

The dashboard is generally installed on the controller node.

#. Ask the cloud operator for the host name or public IP address from
   which you can access the dashboard, and for your user name and
   password. If the cloud supports multi-domain model, you also need to
   ask for your domain name.

#. Open a web browser that has JavaScript and cookies enabled.

   .. note::

      To use the Virtual Network Computing (VNC) client for the dashboard,
      your browser must support HTML5 Canvas and HTML5 WebSockets. The VNC
      client is based on noVNC. For details, see `noVNC: HTML5 VNC
      Client <https://github.com/kanaka/noVNC/blob/master/README.md>`__.
      For a list of supported browsers, see `Browser
      support <https://github.com/kanaka/noVNC/wiki/Browser-support>`__.

#. In the address bar, enter the host name or IP address for the
   dashboard, for example ``https://ipAddressOrHostName/``.

   .. note::

      If a certificate warning appears when you try to access the URL for
      the first time, a self-signed certificate is in use, which is not
      considered trustworthy by default. Verify the certificate or add an
      exception in the browser to bypass the warning.

#. On the Log In page, enter your user name and password, and click
   :guilabel:`Sign In`. If the cloud supports multi-domain model, you also
   need to enter your domain name.

   The top of the window displays your user name. You can also access the
   :guilabel:`Settings` tab (:ref:`dashboard-settings-tab`) or sign out
   of the dashboard.

   The visible tabs and functions in the dashboard depend on the access
   permissions, or roles, of the user you are logged in as.

   * If you are logged in as an end user, the :guilabel:`Project` tab
     (:ref:`dashboard-project-tab`) and :guilabel:`Identity` tab
     (:ref:`dashboard-identity-tab`) are displayed.

   * If you are logged in as an administrator, the :guilabel:`Project` tab
     (:ref:`dashboard-project-tab`) and :guilabel:`Admin` tab
     (:ref:`dashboard-admin-tab`) and :guilabel:`Identity` tab
     (:ref:`dashboard-identity-tab`) are displayed.


.. _dashboard-project-tab:

OpenStack dashboard — :guilabel:`Project` tab
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Projects are organizational units in the cloud, and are also known as
tenants or accounts. Each user is a member of one or more projects.
Within a project, a user creates and manages instances.

From the :guilabel:`Project` tab, you can view and manage the resources in a
selected project, including instances and images. You can select the project
from the drop down menu at the top left. If the cloud supports multi-domain
model, you can also select the domain from this menu.

.. figure:: figures/dashboard_project_tab.png
   :width: 100%

   **Figure: Project tab**

From the :guilabel:`Project` tab, you can access the following categories:

:guilabel:`Compute` tab
-----------------------

* :guilabel:`Overview`: View reports for the project.

* :guilabel:`Instances`: View, launch, create a snapshot from, stop, pause,
  or reboot instances, or connect to them through VNC.

* :guilabel:`Volumes`: Use the following tabs to complete these tasks:

  * :guilabel:`Volumes`: View, create, edit, and delete volumes.

  * :guilabel:`Volume Snapshots`: View, create, edit, and delete volume
    snapshots.

* :guilabel:`Images`: View images and instance snapshots created by project
  users, plus any images that are publicly available. Create, edit, and
  delete images, and launch instances from images and snapshots.

* :guilabel:`Access & Security`: Use the following tabs to complete these
  tasks:

  * :guilabel:`Security Groups`: View, create, edit, and delete security
    groups and security group rules.

  * :guilabel:`Key Pairs`: View, create, edit, import, and delete key pairs.

  * :guilabel:`Floating IPs`: Allocate an IP address to or release it from a
    project.

  * :guilabel:`API Access`: View API endpoints.

:guilabel:`Network` tab
-----------------------

* :guilabel:`Network Topology`: View the network topology.

* :guilabel:`Networks`: Create and manage public and private networks.

* :guilabel:`Routers`: Create and manage routers.

:guilabel:`Orchestration` tab
-----------------------------

* :guilabel:`Stacks`: Use the REST API to orchestrate multiple composite
  cloud applications.

* :guilabel:`Resource Types`: Show a list of all the supported resource
  types for HOT templates.

:guilabel:`Object Store` tab
----------------------------

* :guilabel:`Containers`: Create and manage containers and objects.

.. _dashboard-admin-tab:

OpenStack dashboard — :guilabel:`Admin` tab
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Administrative users can use the :guilabel:`Admin` tab to view usage and to
manage instances, volumes, flavors, images, networks and so on.


.. figure:: figures/dashboard_admin_tab.png
   :width: 100%

   **Figure: Admin tab**

From the :guilabel:`Admin` tab, you can access the following category
to complete these tasks:

:guilabel:`System` tab
----------------------

* :guilabel:`Overview`: View basic reports.

* :guilabel:`Resource Usage`: Use the following tabs to view the following
  usages:

  * :guilabel:`Usage Report`: View the usage report.

  * :guilabel:`Stats`: View the statistics of all resources.

* :guilabel:`Hypervisors`: View the hypervisor summary.

* :guilabel:`Host Aggregates`: View, create, and edit host aggregates.
  View the list of availability zones.

* :guilabel:`Instances`: View, pause, resume, suspend, migrate, soft or hard
  reboot, and delete running instances that belong to users of some, but not
  all, projects. Also, view the log for an instance or access an instance
  through VNC.

* :guilabel:`Volumes`: Use the following tabs to complete these tasks:

  * :guilabel:`Volumes`: View, create, manage, and delete volumes.

  * :guilabel:`Volume Types`: View, create, manage, and delete volume types.

  * :guilabel:`Volume Snapshots`: View, manage, and delete volume snapshots.

* :guilabel:`Flavors`: View, create, edit, view extra specifications for,
  and delete flavors. A flavor is size of an instance.

* :guilabel:`Images`: View, create, edit properties for, and delete custom
  images.

* :guilabel:`Networks`: View, create, edit properties for, and delete
  networks.

* :guilabel:`Routers`: View, create, edit properties for, and delete routers.

* :guilabel:`Defaults`: View default quota values. Quotas are hard-coded in
  OpenStack Compute and define the maximum allowable size and number of
  resources.

* :guilabel:`Metadata Definitions`: Import namespace and view the metadata
  information.

* :guilabel:`System Information`: Use the following tabs to view the service
  information:

  * :guilabel:`Services`: View a list of the services.

  * :guilabel:`Compute Services`: View a list of all Compute services.

  * :guilabel:`Block Storage Services`: View a list of all Block Storage
    services.

  * :guilabel:`Network Agents`: View the network agents.

  * :guilabel:`Orchestration Services`: View a list of all Orchestration
    services.

.. _dashboard-identity-tab:

OpenStack dashboard — :guilabel:`Identity` tab
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: figures/dashboard_identity_tab.png
   :width: 100%

   **Figure:Identity tab**

* :guilabel:`Projects`: View, create, assign users to, remove users from,
  and delete projects.

* :guilabel:`Users`: View, create, enable, disable, and delete users.

.. _dashboard-settings-tab:

OpenStack dashboard — :guilabel:`Settings` tab
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: figures/dashboard_settings_tab.png
   :width: 100%

   **Figure:Settings tab**

Click the :guilabel:`Settings` button from the user drop down menu at the
top right of any page, you will see the :guilabel:`Settings` tab.

* :guilabel:`User Settings`: View and manage dashboard settings.

* :guilabel:`Change Password`: Change the password of the user.
