.. Copyright 2020-present Open Networking Foundation
   Copyright 2022-2024 Intel Corporation
   Copyright 2025 Derek Foster
   SPDX-License-Identifier: Apache 2.0

.. _infrap4d_flags:

========================
Infrap4d Flags Reference
========================

.. contents::
   :depth: 3

This section contains a list of the command-line flags that infrap4d accepts.

Common Flags
============

Flags from auth_policy_checker
------------------------------

``--auth_policy_file_path``
   Path to AuthorizationPolicy proto.
   Only used if ``--enable_authorization`` is true.

   Type: string, default:
   ``"/mnt/region_config/switchstack/keys/authorization_policy.proto.txt"``.

``--enable_authorization``
   Whether to enable per-service, per-RPC authorization checking.
   The default must be true. Set to false only for testing purposes.
   Type: bool, default: false.

``--file_change_poll_timeout_ms``
   Time in ms used as the timeout for file event polling.
   Type: int32, units: milliseconds, default: 100.

``--membership_info_file_path``
   Path to MembershipInfo proto.
   Only used if ``--enable_authorization`` is true.

   Type: string, default:
   ``"/mnt/region_config/switchstack/keys/membership_info.proto.txt"``.

Flags from config_monitoring_service
------------------------------------

``--chassis_config_file``
   The latest verified ChassisConfig proto pushed to the switch.
   This proto is regenerated based on the pushed YANG proto and
   includes the overall running config at any point of time. Default is
   empty and is expected to be explicitly given by flags.

   Type: string, default:
   ``"/usr/share/stratum/es2k/es2k_port_config.pb.txt"`` for ES2K, or
   ``"/usr/share/stratum/dpdk/dpdk_port_config.pb.txt"`` for DPDK.


``--gnmi_capabilities_file``
   Path to the file containing the gNMI capabilities proto.
   Type: string, default: ``"/etc/stratum/gnmi_caps.pb.txt"``.

Flags from credentials_manager
------------------------------

``--ca_cert_file``
   Path to CA certificate file.
   Type: string, default: ``"/usr/share/stratum/certs/ca.crt"``.

``--client_cert_file``
   Path to file containing gRPC client certificate.
   Type: string, default: ``"/usr/share/stratum/certs/client.crt"``.

``--client_cert_req_type``
   Client certificate request type.
   Type: string, default: ``"no_request"``.

``--client_key_file``
   Path to file containing gRPC client key.
   Type: string, default: ``"/usr/share/stratum/certs/client.key"``.

``--server_cert_file``
   Path to file containing gRPC server certificate.
   Type: string, default: ``"/usr/share/stratum/certs/stratum.crt"``.

``--server_key_file``
   Path to file containing gRPC server private key.
   Type: string, default: ``"/usr/share/stratum/certs/stratum.key"``.

Flags from error_buffer
-----------------------

``--max_num_errors_to_track``
   Max number of error statuses to track/save in the buffer.
   Type: int32, default: 10.

Flags from gflags
-----------------

``--flagfile``
   Load flags from file.
   Type: string, default: ``""``.

``--fromenv``
   Set flags from the environment (use ``export FLAGS_flag1=value``).
   Type: string, default: ``""``.

``--tryfromenv``
   Set flags from the environment if present.
   Type: string, default: ``""``.

``--undefok``
   Comma-separated list of flag names that it is okay to specify on
   the command line even if the program does not define a flag with that
   name.

   IMPORTANT: flags in this list that have arguments MUST use the
   ``flag=value`` format.
   Type: string, default: ``""``.

Flags from gflags_completions
-----------------------------

``--tab_completion_columns``
   Number of columns to use in output for tab completion.
   Type: int32, default: 80.

``--tab_completion_word``
   If non-empty, HandleCommandLineCompletions() will hijack the process
   and attempt to do bash-style command line flag completion on this value.
   Type: string, default: ``""``.

Flags from gflags_reporting
---------------------------

``--help``
   Show help on all flags. (Tip: all flags can have one or two dashes).
   Type: bool, default: false.

``--helpfull``
   Show help on all flags -- same as ``-help``.
   Type: bool, default: false.

``--helpmatch``
   Show help on modules whose name contains the specified substr.
   Type: string, default: ``""``.

``--helpon``
   Show help on the modules named by this flag value.
   Type: string, default: ``""``.

``--helppackage``
   Show help on all modules in the main package.
   Type: bool, default: false.

``--helpshort``
   Show help on only the main module for this program.
   Type: bool, default: false.

``--helpxml``
   Produce an xml version of help.
   Type: bool, default: false.

``--version``
   Show version and build info and exit.
   Type: bool, default: false.

Flags from logging
------------------

``--alsologtoemail``
   Log messages go to these email addresses in addition to logfiles.
   Type: string, default: ``""``.

``--alsologtostderr``
   Log messages go to stderr in addition to logfiles.
   Type: bool, default: false.

``--colorlogtostderr``
   Color messages logged to stderr if supported by terminal.
   Type: bool, default: false.

``--colorlogtostdout``
   Color messages logged to stdout if supported by terminal.
   Type: bool, default: false.

``--drop_log_memory``
   Drop in-memory buffers of log contents. Logs can grow very quickly
   and they are rarely read before they need to be evicted from memory.
   Instead, drop them from memory as soon as they are flushed to disk.

   Type: bool, default: true.

``--log_backtrace_at``
   Emit a backtrace when logging at ``file:linenum``.
   Type: string, default: ``""``.

``--log_dir``
   If specified, logfiles are written into this directory instead of
   the default logging directory.

   Type: string, default: ``"/var/log/stratum/"``.

``--log_link``
   Put additional links to the log files in this directory.
   Type: string, default: ``""``.

``--log_prefix``
   Prepend the log prefix to the start of each log line.
   Type: bool, default: true.

``--log_utc_time``
   Use UTC time for logging.
   Type: bool, default: false.

``--log_year_in_prefix``
   Include the year in the log prefix.
   Type: bool, default: true.

``--logbuflevel``
   Buffer log messages logged at this level or lower (-1 means don't
   buffer; 0 means buffer INFO only).
   Type: int32, default: 0.

``--logbufsecs``
   Buffer log messages for at most this many seconds.
   Type: int32, default: 30.

``--logcleansecs``
   Clean overdue logs every this many seconds.
   Type: int32, default: 300.

``--logemaillevel``
   Email log messages logged at this level or higher (0 means email all;
   3 means email FATAL only).
   Type: int32, default: 999.

``--logfile_mode``
   Log file mode/permissions.
   Type: int32, default: 436.

``--logmailer``
   Mailer used to send logging email.
   Type: string, default: ``""``.

``--logtostderr``
   Log messages go to stderr instead of logfiles.
   Type: bool, default: false.

``--logtostdout``
   Log messages go to stdout instead of logfiles.
   Type: bool, default: false.

``--logtosyslog``
   Log messages also go to syslog.
   Type: bool, default: false.

``--max_log_size``
   Approximate maximum log file size inn MB. A value of 0 will be
   silently overridden to 1.
   Type: uint32, default: 1800.

``--minloglevel``
   Messages logged at a lower level than this don't actually get
   logged anywhere.
   Type: int32, default: 0.

``--stderrthreshold``
   Log messages at or above this level are copied to stderr in addition
   to logfiles. This flag replaces ``--alsologtostderr``.

   Type: int32, default: 2.

``--stop_logging_if_full_disk``
   Stop attempting to log to disk if the disk is full.
   Type: bool, default: false.

``--timestamp_in_logfile_name``
   Put a timestamp at the end of the log file name.
   Type: bool, default: true.

Flags from infrap4d_main
------------------------

``--detach``
   Run infrap4d in detached mode.
   Type: bool, default: true.

``--disable_krnlmon``
   Run infrap4d without krnlmon support.
   Type: bool, default: false.

Flags from status_macros
------------------------

``--status_macros_log_stack_trace``
   If set, all errors generated will log a stack trace.
   Type: bool, default: false.

Flags from p4_info_manager
--------------------------

``--skip_p4_min_objects_check``
   When true, the check for minimum required P4 objects is not enforced.
   Type: bool, default: false.

Flags from p4_service
---------------------

``--forwarding_pipeline_configs_file``
   The latest set of verified ForwardingPipelineConfig protos pushed to
   the switch. This file is updated whenever ForwardingPipelineConfig
   proto for switching node is added or modified.

   Type: string, default: ``"/etc/stratum/pipeline_cfg.pb.txt"``.

``--max_num_controller_connections``
   Max number of active/inactive streaming connections from outside
   controllers for all of the nodes combined.
   Type: int32, default: 20.

``--max_num_controllers_per_node``
   Max number of controllers that can manage a node.
   Type: int32, default: 5.

``--read_req_log_file``
   The log file for all the individual read requests and the corresponding
   results. The format for each line is
   ``<timestamp>;<node_id>;<request proto>;<status>``.

   Type: string, default: ``"/var/log/stratum/p4_reads.pb.txt"``.

``--write_req_log_file``
   The log file for all the individual write request updates and the
   corresponding results. The format for each line is:
   ``<timestamp>;<node_id>;<update proto>;<status>``.

   Type: string, default: ``"/var/log/stratum/p4_writes.pb.txt"``.

Flags from tdi_hal_flags
------------------------

``--external_stratum_urls``
   Comma-separated list of URLs for server to listen to for external
   calls from SDN controller, etc.

   Type: string, default: ``"0.0.0.0:9339,0.0.0.0:9559"``.

``--grpc_keepalive_min_ping_interval``
   Grpc keep-alive minimum ping interval.
   Type: int32, default: 10000.

``--grpc_keepalive_permit``
   Grpc keep-alive permit.
   Type: int32, default: 1.

``--grpc_keepalive_time_ms``
   Grpc keep-alive time.
   Type: int32, units: milliseconds, default: 600000.

``--grpc_keepalive_timeout_ms``
   Grpc keep-alive timeout period.
   Type: int32, units: milliseconds, default: 20000.

``--grpc_max_recv_msg_size``
   Grpc server max receive message size (0 = use gRPC default).
   Type: uint32, default: 268435456.

``--grpc_max_send_msg_size``
   Grpc server max send message size (0 = use gRPC default).
   Type: uint32, default: 0.

``--grpc_open_insecure_mode``
   Open grpc server ports in insecure mode for gNMI, gNOI, and P4RT.
   Type: bool, default: false.

``--local_stratum_url``
   URL for listening to local calls from stratum stub.
   Type: string, default: ``"localhost:9559"``.

``--persistent_config_dir``
   The persistent dir where all the config files will be stored.
   Type: string, default: ``"/etc/stratum/"``.

``--warmboot``
   Specifies whether HAL is in warmboot stage.
   Type: bool, default: false.

Flags from tdi_sde_flags
------------------------

``--incompatible_enable_tdi_legacy_bytestring_responses``
   Enables the legacy padded-byte string format in P4Runtime responses
   for Stratum-tdi. The strings are left unchanged from the underlying SDE.

   Type: bool, default: true.

Flags from tdi_sde_wrapper
--------------------------

``--tdi_sde_config_dir``
   The dir used by the SDE to load the device configuration.

   Type: string, default: ``"/var/run/stratum/tdi_config"``.

Flags from tdi_table_manager
----------------------------

``--tdi_table_sync_timeout_ms``
   The timeout for table sync operation like counters and registers.
   Type: uint32, units: milliseconds, default: 1000.

Flags from utilities
--------------------

``--symbolize_stacktrace``
   Symbolize the stack trace in the tombstone.
   Type: bool, default: true.

Flags from vlog_is_on
---------------------

``--v``
   Show all VLOG messages for m <= this. Overridable by ``--vmodule``.
   Type: int32, default: 0.

``--vmodule``
   Per-module verbose level. Argument is a comma-separated list of
   ``<module name>=<log level>``.

   - *<module name>* is a glob pattern, matched against the filename
     base (excluding ``.cc``, ``.h``, and ``-inl.h``).
   - *<log level>* overrides any value given by ``--v``.

   Type: string, default: ``""``.

DPDK Flags
==========

Flags from dpdk_main
--------------------

``--dpdk_infrap4d_cfg``
  Path to the infrap4d json config file.

  Type: string, default: ``"/usr/share/stratum/dpdk/dpdk_skip_p4.conf"``.

``--dpdk_sde_install``
  Absolute path to the directory where the SDE is installed.

  Type: string, default: ``"/usr"``.

ES2K Flags
==========

Flags from es2k_main
--------------------

``--es2k_infrap4d_cfg``
   Path to the infrap4d json config file.

   Type: string, default: ``"/usr/share/stratum/es2k/es2k_skip_p4.conf"``.

``--es2k_sde_install``
   Absolute path to the directory where the SDE is installed.

   Type: string, default: ``"/usr"``.

Flags from es2k_node
--------------------

``--enable_sticky_tdi_session``
   Use a persistent TDI session to write forwarding entries.
   Type: bool, default: false.

