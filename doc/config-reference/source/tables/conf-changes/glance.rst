New, updated, and deprecated options in Mitaka for Image service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
  Warning: Do not edit this file. It is automatically generated and your
  changes will be overwritten. The tool to do so lives in the
  openstack-doc-tools repository.

.. list-table:: New options
   :header-rows: 1
   :class: config-ref-table

   * - Option = default value
     - (Type) Help string
   * - ``[profiler] hmac_keys = SECRET_KEY``
     - ``(StrOpt) Secret key to use to sign Glance API and Glance Registry services tracing messages.``

.. list-table:: New default values
   :header-rows: 1
   :class: config-ref-table

   * - Option
     - Previous default value
     - New default value
   * - ``[DEFAULT] allowed_rpc_exception_modules``
     - ``glance.common.exception, exceptions``
     - ``glance.common.exception, builtins, exceptions``
   * - ``[DEFAULT] workers``
     - ``4``
     - ``None``
   * - ``[image_format] container_formats``
     - ``ami, ari, aki, bare, ovf, ova``
     - ``ami, ari, aki, bare, ovf, ova, docker``

.. list-table:: Deprecated options
   :header-rows: 1
   :class: config-ref-table

   * - Deprecated option
     - New Option
   * - ``[DEFAULT] use_syslog``
     - ``None``

