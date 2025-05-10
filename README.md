reth
=========

reth execution layer

**Tests:**
* Ubuntu 22.04 (jammy)

How to run molecule tests
----------------------

```shell
python3 -m venv venv
pip install -r requirements.txt
source venv/bin/activate
make init
make test
```

Make
----

`make init` - Prepare environment
`make test` - Run molecule tests (`molecule -v test`)
`make docs` - Auto-generate `README` (`ansible-doctor`)

Role install
--------------

You can install role by using `ansible-galaxy`:

```shell
ansible-galaxy role install git+git@github.com:keynodes-org/ansible_reth.git
```

For particular version of this role:
```shell
ansible-galaxy role install git+git@github.com:keynodes-org/ansible_reth.git,main
```

Update to latest version:
```shell
ansible-galaxy role install git+git@github.com:keynodes-org/ansible_reth.git --upgrade
```

Example of using in `requirements.yml`:
```yaml
---
roles:
  - name: reth
    src: git+git@github.com:keynodes-org/ansible_reth.git
    version: main
```

How to use in playbook:
-------------------------

```yaml
- hosts: ansible_hostname
  roles:
    - role: ansible_reth
```

Variables
===============

Ansible role for deploying Reth Ethereum Execution layer node

## Auto-generated

- [Defaults](#default-vars)
  - [reth_addr](#reth_addr)
  - [reth_auth_ipc](#reth_auth_ipc)
  - [reth_auth_ipc_path](#reth_auth_ipc_path)
  - [reth_authrpc_addr](#reth_authrpc_addr)
  - [reth_authrpc_jwtsecret](#reth_authrpc_jwtsecret)
  - [reth_authrpc_port](#reth_authrpc_port)
  - [reth_binary_download_url](#reth_binary_download_url)
  - [reth_binary_path](#reth_binary_path)
  - [reth_blobpool_pricebump](#reth_blobpool_pricebump)
  - [reth_block_interval](#reth_block_interval)
  - [reth_bootnodes](#reth_bootnodes)
  - [reth_builder_deadline](#reth_builder_deadline)
  - [reth_builder_disallow](#reth_builder_disallow)
  - [reth_builder_extradata](#reth_builder_extradata)
  - [reth_builder_gaslimit](#reth_builder_gaslimit)
  - [reth_builder_interval](#reth_builder_interval)
  - [reth_builder_max_tasks](#reth_builder_max_tasks)
  - [reth_chain](#reth_chain)
  - [reth_cli_custom_flags](#reth_cli_custom_flags)
  - [reth_cli_custom_options](#reth_cli_custom_options)
  - [reth_cli_default_flags](#reth_cli_default_flags)
  - [reth_cli_default_options](#reth_cli_default_options)
  - [reth_color](#reth_color)
  - [reth_config_file](#reth_config_file)
  - [reth_datadir_static_files](#reth_datadir_static_files)
  - [reth_db_exclusive](#reth_db_exclusive)
  - [reth_db_growth_step](#reth_db_growth_step)
  - [reth_db_log_level](#reth_db_log_level)
  - [reth_db_max_size](#reth_db_max_size)
  - [reth_db_read_transaction_timeout](#reth_db_read_transaction_timeout)
  - [reth_debug_engine_api_store](#reth_debug_engine_api_store)
  - [reth_debug_etherscan](#reth_debug_etherscan)
  - [reth_debug_healthy_node_rpc_url](#reth_debug_healthy_node_rpc_url)
  - [reth_debug_invalid_block_hook](#reth_debug_invalid_block_hook)
  - [reth_debug_max_block](#reth_debug_max_block)
  - [reth_debug_reorg_depth](#reth_debug_reorg_depth)
  - [reth_debug_reorg_frequency](#reth_debug_reorg_frequency)
  - [reth_debug_rpc_consensus_ws](#reth_debug_rpc_consensus_ws)
  - [reth_debug_skip_fcu](#reth_debug_skip_fcu)
  - [reth_debug_skip_new_payload](#reth_debug_skip_new_payload)
  - [reth_debug_terminate](#reth_debug_terminate)
  - [reth_debug_tip](#reth_debug_tip)
  - [reth_dev](#reth_dev)
  - [reth_dev_block_max_transactions](#reth_dev_block_max_transactions)
  - [reth_dev_block_time](#reth_dev_block_time)
  - [reth_dir_base](#reth_dir_base)
  - [reth_dir_binary](#reth_dir_binary)
  - [reth_dir_config](#reth_dir_config)
  - [reth_dir_data](#reth_dir_data)
  - [reth_dir_data_static_files](#reth_dir_data_static_files)
  - [reth_dir_log](#reth_dir_log)
  - [reth_dir_systemd](#reth_dir_systemd)
  - [reth_disable_discovery](#reth_disable_discovery)
  - [reth_disable_discv4_discovery](#reth_disable_discv4_discovery)
  - [reth_disable_dns_discovery](#reth_disable_dns_discovery)
  - [reth_disable_nat](#reth_disable_nat)
  - [reth_discovery_addr](#reth_discovery_addr)
  - [reth_discovery_port](#reth_discovery_port)
  - [reth_discovery_v5_addr](#reth_discovery_v5_addr)
  - [reth_discovery_v5_addr_ipv6](#reth_discovery_v5_addr_ipv6)
  - [reth_discovery_v5_bootstrap_lookup_countdown](#reth_discovery_v5_bootstrap_lookup_countdown)
  - [reth_discovery_v5_bootstrap_lookup_interval](#reth_discovery_v5_bootstrap_lookup_interval)
  - [reth_discovery_v5_lookup_interval](#reth_discovery_v5_lookup_interval)
  - [reth_discovery_v5_port](#reth_discovery_v5_port)
  - [reth_discovery_v5_port_ipv6](#reth_discovery_v5_port_ipv6)
  - [reth_dns_retries](#reth_dns_retries)
  - [reth_enable_discv5_discovery](#reth_enable_discv5_discovery)
  - [reth_engine_accept_execution_requests_hash](#reth_engine_accept_execution_requests_hash)
  - [reth_engine_cross_block_cache_size](#reth_engine_cross_block_cache_size)
  - [reth_engine_disable_caching_and_prewarming](#reth_engine_disable_caching_and_prewarming)
  - [reth_engine_legacy_state_root](#reth_engine_legacy_state_root)
  - [reth_engine_max_proof_task_concurrency](#reth_engine_max_proof_task_concurrency)
  - [reth_engine_memory_block_buffer_target](#reth_engine_memory_block_buffer_target)
  - [reth_engine_persistence_threshold](#reth_engine_persistence_threshold)
  - [reth_engine_reserved_cpu_cores](#reth_engine_reserved_cpu_cores)
  - [reth_engine_state_provider_metrics](#reth_engine_state_provider_metrics)
  - [reth_engine_state_root_task_compare_updates](#reth_engine_state_root_task_compare_updates)
  - [reth_extra_systemd_directives](#reth_extra_systemd_directives)
  - [reth_full](#reth_full)
  - [reth_general_owner](#reth_general_owner)
  - [reth_gpo_blocks](#reth_gpo_blocks)
  - [reth_gpo_ignoreprice](#reth_gpo_ignoreprice)
  - [reth_gpo_maxprice](#reth_gpo_maxprice)
  - [reth_gpo_percentile](#reth_gpo_percentile)
  - [reth_group](#reth_group)
  - [reth_http_addr](#reth_http_addr)
  - [reth_http_api](#reth_http_api)
  - [reth_http_corsdomain](#reth_http_corsdomain)
  - [reth_http_port](#reth_http_port)
  - [reth_identity](#reth_identity)
  - [reth_instance](#reth_instance)
  - [reth_ipcdisable](#reth_ipcdisable)
  - [reth_ipcpath](#reth_ipcpath)
  - [reth_jwt_secret_path](#reth_jwt_secret_path)
  - [reth_limit_nofile](#reth_limit_nofile)
  - [reth_log_file_directory](#reth_log_file_directory)
  - [reth_log_file_filter](#reth_log_file_filter)
  - [reth_log_file_format](#reth_log_file_format)
  - [reth_log_file_max_files](#reth_log_file_max_files)
  - [reth_log_file_max_size](#reth_log_file_max_size)
  - [reth_log_journald](#reth_log_journald)
  - [reth_log_journald_filter](#reth_log_journald_filter)
  - [reth_log_stdout_filter](#reth_log_stdout_filter)
  - [reth_log_stdout_format](#reth_log_stdout_format)
  - [reth_max_inbound_peers](#reth_max_inbound_peers)
  - [reth_max_outbound_peers](#reth_max_outbound_peers)
  - [reth_max_pending_imports](#reth_max_pending_imports)
  - [reth_max_seen_tx_history](#reth_max_seen_tx_history)
  - [reth_max_tx_pending_fetch](#reth_max_tx_pending_fetch)
  - [reth_max_tx_reqs](#reth_max_tx_reqs)
  - [reth_max_tx_reqs_peer](#reth_max_tx_reqs_peer)
  - [reth_metrics_listen_addr](#reth_metrics_listen_addr)
  - [reth_metrics_listen_port](#reth_metrics_listen_port)
  - [reth_nat](#reth_nat)
  - [reth_net_if_experimental](#reth_net_if_experimental)
  - [reth_no_persist_peers](#reth_no_persist_peers)
  - [reth_p2p_secret_key](#reth_p2p_secret_key)
  - [reth_peers_backoff_durations_high](#reth_peers_backoff_durations_high)
  - [reth_peers_backoff_durations_low](#reth_peers_backoff_durations_low)
  - [reth_peers_backoff_durations_max](#reth_peers_backoff_durations_max)
  - [reth_peers_backoff_durations_medium](#reth_peers_backoff_durations_medium)
  - [reth_peers_ban_duration](#reth_peers_ban_duration)
  - [reth_peers_connection_info_max_concurrent_outbound_dials](#reth_peers_connection_info_max_concurrent_outbound_dials)
  - [reth_peers_connection_info_max_inbound](#reth_peers_connection_info_max_inbound)
  - [reth_peers_connection_info_max_outbound](#reth_peers_connection_info_max_outbound)
  - [reth_peers_file](#reth_peers_file)
  - [reth_peers_incoming_ip_throttle_duration](#reth_peers_incoming_ip_throttle_duration)
  - [reth_peers_max_backoff_count](#reth_peers_max_backoff_count)
  - [reth_peers_refill_slots_interval](#reth_peers_refill_slots_interval)
  - [reth_peers_reputation_weights_already_seen_transactions](#reth_peers_reputation_weights_already_seen_transactions)
  - [reth_peers_reputation_weights_bad_announcement](#reth_peers_reputation_weights_bad_announcement)
  - [reth_peers_reputation_weights_bad_block](#reth_peers_reputation_weights_bad_block)
  - [reth_peers_reputation_weights_bad_message](#reth_peers_reputation_weights_bad_message)
  - [reth_peers_reputation_weights_bad_protocol](#reth_peers_reputation_weights_bad_protocol)
  - [reth_peers_reputation_weights_bad_transactions](#reth_peers_reputation_weights_bad_transactions)
  - [reth_peers_reputation_weights_dropped](#reth_peers_reputation_weights_dropped)
  - [reth_peers_reputation_weights_failed_to_connect](#reth_peers_reputation_weights_failed_to_connect)
  - [reth_peers_reputation_weights_timeout](#reth_peers_reputation_weights_timeout)
  - [reth_peers_trusted_nodes](#reth_peers_trusted_nodes)
  - [reth_peers_trusted_nodes_only](#reth_peers_trusted_nodes_only)
  - [reth_pooled_tx_pack_soft_limit](#reth_pooled_tx_pack_soft_limit)
  - [reth_pooled_tx_response_soft_limit](#reth_pooled_tx_response_soft_limit)
  - [reth_port](#reth_port)
  - [reth_prune_accounthistory_before](#reth_prune_accounthistory_before)
  - [reth_prune_accounthistory_distance](#reth_prune_accounthistory_distance)
  - [reth_prune_accounthistory_full](#reth_prune_accounthistory_full)
  - [reth_prune_receipts_before](#reth_prune_receipts_before)
  - [reth_prune_receipts_distance](#reth_prune_receipts_distance)
  - [reth_prune_receipts_full](#reth_prune_receipts_full)
  - [reth_prune_receiptslogfilter](#reth_prune_receiptslogfilter)
  - [reth_prune_senderrecovery_before](#reth_prune_senderrecovery_before)
  - [reth_prune_senderrecovery_distance](#reth_prune_senderrecovery_distance)
  - [reth_prune_senderrecovery_full](#reth_prune_senderrecovery_full)
  - [reth_prune_storagehistory_before](#reth_prune_storagehistory_before)
  - [reth_prune_storagehistory_distance](#reth_prune_storagehistory_distance)
  - [reth_prune_storagehistory_full](#reth_prune_storagehistory_full)
  - [reth_prune_transactionlookup_before](#reth_prune_transactionlookup_before)
  - [reth_prune_transactionlookup_distance](#reth_prune_transactionlookup_distance)
  - [reth_prune_transactionlookup_full](#reth_prune_transactionlookup_full)
  - [reth_quiet](#reth_quiet)
  - [reth_reinstall](#reth_reinstall)
  - [reth_ress_enable](#reth_ress_enable)
  - [reth_ress_max_active_connections](#reth_ress_max_active_connections)
  - [reth_ress_max_witness_window](#reth_ress_max_witness_window)
  - [reth_ress_witness_cache_size](#reth_ress_witness_cache_size)
  - [reth_ress_witness_max_parallel](#reth_ress_witness_max_parallel)
  - [reth_restart_policy](#reth_restart_policy)
  - [reth_restart_sec](#reth_restart_sec)
  - [reth_rpc_cache_max_blocks](#reth_rpc_cache_max_blocks)
  - [reth_rpc_cache_max_concurrent_db_requests](#reth_rpc_cache_max_concurrent_db_requests)
  - [reth_rpc_cache_max_headers](#reth_rpc_cache_max_headers)
  - [reth_rpc_cache_max_receipts](#reth_rpc_cache_max_receipts)
  - [reth_rpc_eth_proof_window](#reth_rpc_eth_proof_window)
  - [reth_rpc_gascap](#reth_rpc_gascap)
  - [reth_rpc_jwtsecret](#reth_rpc_jwtsecret)
  - [reth_rpc_max_blocks_per_filter](#reth_rpc_max_blocks_per_filter)
  - [reth_rpc_max_connections](#reth_rpc_max_connections)
  - [reth_rpc_max_logs_per_response](#reth_rpc_max_logs_per_response)
  - [reth_rpc_max_request_size](#reth_rpc_max_request_size)
  - [reth_rpc_max_response_size](#reth_rpc_max_response_size)
  - [reth_rpc_max_simulate_blocks](#reth_rpc_max_simulate_blocks)
  - [reth_rpc_max_subscriptions_per_connection](#reth_rpc_max_subscriptions_per_connection)
  - [reth_rpc_max_trace_filter_blocks](#reth_rpc_max_trace_filter_blocks)
  - [reth_rpc_max_tracing_requests](#reth_rpc_max_tracing_requests)
  - [reth_rpc_proof_permits](#reth_rpc_proof_permits)
  - [reth_rpc_txfeecap](#reth_rpc_txfeecap)
  - [reth_sessions_initial_internal_request_timeout_nanos](#reth_sessions_initial_internal_request_timeout_nanos)
  - [reth_sessions_initial_internal_request_timeout_secs](#reth_sessions_initial_internal_request_timeout_secs)
  - [reth_sessions_pending_session_timeout_nanos](#reth_sessions_pending_session_timeout_nanos)
  - [reth_sessions_pending_session_timeout_secs](#reth_sessions_pending_session_timeout_secs)
  - [reth_sessions_protocol_breach_request_timeout_nanos](#reth_sessions_protocol_breach_request_timeout_nanos)
  - [reth_sessions_protocol_breach_request_timeout_secs](#reth_sessions_protocol_breach_request_timeout_secs)
  - [reth_sessions_session_command_buffer](#reth_sessions_session_command_buffer)
  - [reth_sessions_session_event_buffer](#reth_sessions_session_event_buffer)
  - [reth_stages_account_hashing_clean_threshold](#reth_stages_account_hashing_clean_threshold)
  - [reth_stages_account_hashing_commit_threshold](#reth_stages_account_hashing_commit_threshold)
  - [reth_stages_bodies_downloader_max_buffered_blocks_size_bytes](#reth_stages_bodies_downloader_max_buffered_blocks_size_bytes)
  - [reth_stages_bodies_downloader_max_concurrent_requests](#reth_stages_bodies_downloader_max_concurrent_requests)
  - [reth_stages_bodies_downloader_min_concurrent_requests](#reth_stages_bodies_downloader_min_concurrent_requests)
  - [reth_stages_bodies_downloader_request_limit](#reth_stages_bodies_downloader_request_limit)
  - [reth_stages_bodies_downloader_stream_batch_size](#reth_stages_bodies_downloader_stream_batch_size)
  - [reth_stages_etl_file_size](#reth_stages_etl_file_size)
  - [reth_stages_execution_max_blocks](#reth_stages_execution_max_blocks)
  - [reth_stages_execution_max_changes](#reth_stages_execution_max_changes)
  - [reth_stages_execution_max_cumulative_gas](#reth_stages_execution_max_cumulative_gas)
  - [reth_stages_execution_max_duration](#reth_stages_execution_max_duration)
  - [reth_stages_headers_commit_threshold](#reth_stages_headers_commit_threshold)
  - [reth_stages_headers_downloader_max_buffered_responses](#reth_stages_headers_downloader_max_buffered_responses)
  - [reth_stages_headers_downloader_max_concurrent_requests](#reth_stages_headers_downloader_max_concurrent_requests)
  - [reth_stages_headers_downloader_min_concurrent_requests](#reth_stages_headers_downloader_min_concurrent_requests)
  - [reth_stages_headers_downloader_request_limit](#reth_stages_headers_downloader_request_limit)
  - [reth_stages_index_account_history_commit_threshold](#reth_stages_index_account_history_commit_threshold)
  - [reth_stages_index_storage_history_commit_threshold](#reth_stages_index_storage_history_commit_threshold)
  - [reth_stages_merkle_clean_threshold](#reth_stages_merkle_clean_threshold)
  - [reth_stages_prune_commit_threshold](#reth_stages_prune_commit_threshold)
  - [reth_stages_sender_recovery_commit_threshold](#reth_stages_sender_recovery_commit_threshold)
  - [reth_stages_storage_hashing_clean_threshold](#reth_stages_storage_hashing_clean_threshold)
  - [reth_stages_storage_hashing_commit_threshold](#reth_stages_storage_hashing_commit_threshold)
  - [reth_stages_transaction_lookup_chunk_size](#reth_stages_transaction_lookup_chunk_size)
  - [reth_stop_timeout_sec](#reth_stop_timeout_sec)
  - [reth_systemd_limit_nofile](#reth_systemd_limit_nofile)
  - [reth_systemd_restart_policy](#reth_systemd_restart_policy)
  - [reth_systemd_restart_sec](#reth_systemd_restart_sec)
  - [reth_systemd_service_name](#reth_systemd_service_name)
  - [reth_systemd_stop_timeout_sec](#reth_systemd_stop_timeout_sec)
  - [reth_trusted_only](#reth_trusted_only)
  - [reth_trusted_peers](#reth_trusted_peers)
  - [reth_tx_propagation_policy](#reth_tx_propagation_policy)
  - [reth_txpool_additional_validation_tasks](#reth_txpool_additional_validation_tasks)
  - [reth_txpool_basefee_max_count](#reth_txpool_basefee_max_count)
  - [reth_txpool_basefee_max_size](#reth_txpool_basefee_max_size)
  - [reth_txpool_blob_cache_size](#reth_txpool_blob_cache_size)
  - [reth_txpool_blobpool_max_count](#reth_txpool_blobpool_max_count)
  - [reth_txpool_blobpool_max_size](#reth_txpool_blobpool_max_size)
  - [reth_txpool_disable_transactions_backup](#reth_txpool_disable_transactions_backup)
  - [reth_txpool_gas_limit](#reth_txpool_gas_limit)
  - [reth_txpool_lifetime](#reth_txpool_lifetime)
  - [reth_txpool_locals](#reth_txpool_locals)
  - [reth_txpool_max_account_slots](#reth_txpool_max_account_slots)
  - [reth_txpool_max_cached_entries](#reth_txpool_max_cached_entries)
  - [reth_txpool_max_new_pending_txs_notifications](#reth_txpool_max_new_pending_txs_notifications)
  - [reth_txpool_max_new_txns](#reth_txpool_max_new_txns)
  - [reth_txpool_max_pending_txns](#reth_txpool_max_pending_txns)
  - [reth_txpool_max_tx_input_bytes](#reth_txpool_max_tx_input_bytes)
  - [reth_txpool_minimal_protocol_fee](#reth_txpool_minimal_protocol_fee)
  - [reth_txpool_no_local_transactions_propagation](#reth_txpool_no_local_transactions_propagation)
  - [reth_txpool_nolocals](#reth_txpool_nolocals)
  - [reth_txpool_pending_max_count](#reth_txpool_pending_max_count)
  - [reth_txpool_pending_max_size](#reth_txpool_pending_max_size)
  - [reth_txpool_pricebump](#reth_txpool_pricebump)
  - [reth_txpool_queued_max_count](#reth_txpool_queued_max_count)
  - [reth_txpool_queued_max_size](#reth_txpool_queued_max_size)
  - [reth_txpool_transactions_backup](#reth_txpool_transactions_backup)
  - [reth_user](#reth_user)
  - [reth_verbosity](#reth_verbosity)
  - [reth_with_unused_ports](#reth_with_unused_ports)
  - [reth_ws_addr](#reth_ws_addr)
  - [reth_ws_api](#reth_ws_api)
  - [reth_ws_origins](#reth_ws_origins)
  - [reth_ws_port](#reth_ws_port)
- [Tags](#tags)

- [Dependencies](#dependencies)

---

## Defaults

### reth_addr

Network listening address.

#### Defaults

```YAML
reth_addr: 0.0.0.0
```

### reth_auth_ipc

Enable auth engine API over IPC.

#### Defaults

```YAML
reth_auth_ipc: false
```

### reth_auth_ipc_path

Filename for auth IPC socket/pipe within the datadir.

#### Defaults

```YAML
reth_auth_ipc_path: <CACHE_DIR>_engine_api.ipc
```

### reth_authrpc_addr

Auth server address to listen on.

#### Defaults

```YAML
reth_authrpc_addr: 127.0.0.1
```

### reth_authrpc_jwtsecret

Path to a JWT secret to use for the authenticated engine-API RPC server.

#### Defaults

```YAML
reth_authrpc_jwtsecret: '{{ reth_dir_config }}/jwt.hex'
```

### reth_authrpc_port

Auth server port to listen on.

#### Defaults

```YAML
reth_authrpc_port: 8551
```

### reth_binary_download_url

URL to download the reth binary.

#### Defaults

```YAML
reth_binary_download_url: https://github.com/paradigmxyz/reth/releases/download/v1.3.12/reth-v1.3.12-x86_64-unknown-linux-gnu.tar.gz
```

### reth_binary_path

Path the reth binary.

#### Defaults

```YAML
reth_binary_path: '{{ reth_dir_binary }}/reth'
```

### reth_blobpool_pricebump

Price bump percentage to replace an already existing blob transaction.

#### Defaults

```YAML
reth_blobpool_pricebump: 100
```

### reth_block_interval

Minimum pruning interval measured in blocks.

#### Defaults

```YAML
reth_block_interval: <BLOCK_COUNT>
```

### reth_bootnodes

Comma separated enode URLs for P2P discovery bootstrap. Will fall back to a network-specific default if not specified.

#### Defaults

```YAML
reth_bootnodes: ''
```

### reth_builder_deadline

The deadline in seconds for when the payload builder job should resolve.

#### Defaults

```YAML
reth_builder_deadline: 12
```

### reth_builder_disallow

Path to file containing disallowed addresses, json-encoded list of strings. Block validation API will reject blocks containing transactions from these addresses.

#### Defaults

```YAML
reth_builder_disallow: <PATH_TO_DISALLOW_FILE>
```

### reth_builder_extradata

Block extra data set by the payload builder.

#### Defaults

```YAML
reth_builder_extradata: reth/<VERSION>/<OS>
```

### reth_builder_gaslimit

Target gas limit for built blocks.

#### Defaults

```YAML
reth_builder_gaslimit: 36000000
```

### reth_builder_interval

The interval at which the job should build a new payload after the last. Interval is specified in seconds or in milliseconds if the value ends with `ms`: e.g., `50ms` or `1`.

#### Defaults

```YAML
reth_builder_interval: '1'
```

### reth_builder_max_tasks

Maximum number of tasks to spawn for building a payload.

#### Defaults

```YAML
reth_builder_max_tasks: 3
```

### reth_chain

The network of the Ethereum chain.

#### Defaults

```YAML
reth_chain: sepolia
```

### reth_cli_custom_flags

 A list of additional, literal command-line flags for the reth node. Each item is a complete flag string, e.g., "--full" or "--txpool.max-account-slots=32".

### reth_cli_custom_options

#### Defaults

```YAML
reth_cli_custom_options: []
```

### reth_cli_default_flags

 A list of commonly used CLI flag strings for the Reth node. Each 'name' string should ideally be a complete CLI flag. If a value is templated (e.g., --option={{ var }}), 'var' should be defined. The presence of an item in this list implies the flag should be considered for addition.

### reth_cli_default_options

#### Defaults

```YAML
reth_cli_default_options:
  - --full
  - --http
  - --http.addr={{ reth_http_addr }}
  - --http.port={{ reth_http_port }}
  - --http.api={{ reth_http_api }}
  - --authrpc.addr={{ reth_authrpc_addr }}
  - --authrpc.port={{ reth_authrpc_port }}
  - --metrics={{ reth_metrics_listen_addr }}:{{ reth_metrics_listen_port }}
  - --authrpc.jwtsecret={{ reth_authrpc_jwtsecret }}
  - --log.file.directory={{ reth_dir_log }}
  - '{{ reth_verbosity }}'
```

### reth_color

Sets whether or not the formatter emits ANSI terminal escape codes for colors and other text formatting. Possible values: always, auto, never.

#### Defaults

```YAML
reth_color: always
```

### reth_config_file

The path to the TOML configuration file to use.

#### Defaults

```YAML
reth_config_file: '{{ reth_dir_config }}/config.toml'
```

### reth_datadir_static_files

The absolute path to store static files in.

### reth_db_exclusive

Open environment in exclusive/monopolistic mode. Makes it possible to open a database on an NFS volume. Possible values: true, false.

#### Defaults

```YAML
reth_db_exclusive: 'false'
```

### reth_db_growth_step

Database growth step (e.g., 4GB, 4KB).

#### Defaults

```YAML
reth_db_growth_step: 256MB
```

### reth_db_log_level

Database logging level. Levels higher than "notice" require a debug build. Possible values: fatal, error, warn, notice, verbose, debug, trace, extra.

#### Defaults

```YAML
reth_db_log_level: notice
```

### reth_db_max_size

Maximum database size (e.g., 4TB, 8MB).

#### Defaults

```YAML
reth_db_max_size: 2TB
```

### reth_db_read_transaction_timeout

Read transaction timeout in seconds, 0 means no timeout.

#### Defaults

```YAML
reth_db_read_transaction_timeout: 10
```

### reth_debug_engine_api_store

The path to store engine API messages at. If specified, all intercepted engine API messages will be written to specified location.

#### Defaults

```YAML
reth_debug_engine_api_store: '{{ reth_dir_data }}'
```

### reth_debug_etherscan

Runs a fake consensus client that advances the chain using recent block hashes on Etherscan. If specified without a URL, uses default Etherscan API. Requires ETHERSCAN_API_KEY env var. Can take an optional ETHERSCAN_API_URL.

#### Defaults

```YAML
reth_debug_etherscan: <OPTIONAL_ETHERSCAN_API_URL_OR_true_TO_ENABLE>
```

### reth_debug_healthy_node_rpc_url

The RPC URL of a healthy node to use for comparing invalid block hook results against.

#### Defaults

```YAML
reth_debug_healthy_node_rpc_url: ''
```

### reth_debug_invalid_block_hook

Determines which type of invalid block hook to install. Example: `witness,prestate`. Possible values: witness, pre-state, opcode. Comma-separated.

#### Defaults

```YAML
reth_debug_invalid_block_hook: witness
```

### reth_debug_max_block

Runs the sync only up to the specified block.

#### Defaults

```YAML
reth_debug_max_block: ''
```

### reth_debug_reorg_depth

The reorg depth for chain reorgs.

#### Defaults

```YAML
reth_debug_reorg_depth: <DEPTH>
```

### reth_debug_reorg_frequency

If provided, the chain will be reorged at specified frequency.

#### Defaults

```YAML
reth_debug_reorg_frequency: <FREQUENCY>
```

### reth_debug_rpc_consensus_ws

Runs a fake consensus client using blocks fetched from an RPC WebSocket endpoint.

#### Defaults

```YAML
reth_debug_rpc_consensus_ws: <RPC_WEBSOCKET_URL>
```

### reth_debug_skip_fcu

If provided, the engine will skip `n` consecutive FCUs.

#### Defaults

```YAML
reth_debug_skip_fcu: <NUMBER_OF_FCUS_TO_SKIP>
```

### reth_debug_skip_new_payload

If provided, the engine will skip `n` consecutive new payloads.

#### Defaults

```YAML
reth_debug_skip_new_payload: <NUMBER_OF_PAYLOADS_TO_SKIP>
```

### reth_debug_terminate

Flag indicating whether the node should be terminated after the pipeline sync.

#### Defaults

```YAML
reth_debug_terminate: false
```

### reth_debug_tip

Set the chain tip manually for testing purposes. NOTE: This is a temporary flag.

#### Defaults

```YAML
reth_debug_tip: ''
```

### reth_dev

Start the node in dev mode. This mode uses a local proof-of-authority consensus engine with either fixed block times or automatically mined blocks. Disables network discovery and enables local http server. Prefunds 20 accounts derived by mnemonic "test test test test test test test test test test test junk" with 10 000 ETH each.

#### Defaults

```YAML
reth_dev: false
```

### reth_dev_block_max_transactions

How many transactions to mine per block in dev mode.

#### Defaults

```YAML
reth_dev_block_max_transactions: <COUNT>
```

### reth_dev_block_time

Interval between blocks in dev mode. Parses strings using humantime::parse_duration (e.g., "12s").

#### Defaults

```YAML
reth_dev_block_time: <DURATION>
```

### reth_dir_base

Base directory for reth installation.

#### Defaults

```YAML
reth_dir_base: /opt/reth
```

### reth_dir_binary

#### Defaults

```YAML
reth_dir_binary: /usr/local/bin
```

### reth_dir_config

Directory for reth configuration files.

#### Defaults

```YAML
reth_dir_config: '{{ reth_dir_base }}/config'
```

### reth_dir_data

Directory for reth data storage.

#### Defaults

```YAML
reth_dir_data: '{{ reth_dir_base }}/data'
```

### reth_dir_data_static_files

#### Defaults

```YAML
reth_dir_data_static_files: '{{ reth_dir_data }}/static'
```

### reth_dir_log

Directory for reth log files.

#### Defaults

```YAML
reth_dir_log: '{{ reth_dir_base }}/logs'
```

### reth_dir_systemd

Systemd service directory for reth.

#### Defaults

```YAML
reth_dir_systemd: /lib/systemd/system
```

### reth_disable_discovery

Disable the discovery service.

#### Defaults

```YAML
reth_disable_discovery: false
```

### reth_disable_discv4_discovery

Disable Discv4 discovery.

#### Defaults

```YAML
reth_disable_discv4_discovery: false
```

### reth_disable_dns_discovery

Disable the DNS discovery.

#### Defaults

```YAML
reth_disable_dns_discovery: false
```

### reth_disable_nat

Disable Nat discovery.

#### Defaults

```YAML
reth_disable_nat: false
```

### reth_discovery_addr

The UDP address to use for devp2p peer discovery version 4.

#### Defaults

```YAML
reth_discovery_addr: 0.0.0.0
```

### reth_discovery_port

The UDP port to use for devp2p peer discovery version 4.

#### Defaults

```YAML
reth_discovery_port: 30303
```

### reth_discovery_v5_addr

The UDP IPv4 address to use for devp2p peer discovery version 5. Overwritten by `RLPx` address, if it's also IPv4.

#### Defaults

```YAML
reth_discovery_v5_addr: '{{ ansible_default_ipv4 }}'
```

### reth_discovery_v5_addr_ipv6

The UDP IPv6 address to use for devp2p peer discovery version 5. Overwritten by `RLPx` address, if it's also IPv6.

#### Defaults

```YAML
reth_discovery_v5_addr_ipv6: '{{ ansible_default_ipv6 }}'
```

### reth_discovery_v5_bootstrap_lookup_countdown

The number of times to carry out boost lookup queries at bootstrap.

#### Defaults

```YAML
reth_discovery_v5_bootstrap_lookup_countdown: 200
```

### reth_discovery_v5_bootstrap_lookup_interval

The interval in seconds at which to carry out boost lookup queries, for a fixed number of times, at bootstrap.

#### Defaults

```YAML
reth_discovery_v5_bootstrap_lookup_interval: 5
```

### reth_discovery_v5_lookup_interval

The interval in seconds at which to carry out periodic lookup queries, for the whole run of the program.

#### Defaults

```YAML
reth_discovery_v5_lookup_interval: 20
```

### reth_discovery_v5_port

The UDP IPv4 port to use for devp2p peer discovery version 5. Not used unless `--addr` is IPv4, or `--discovery.v5.addr` is set.

#### Defaults

```YAML
reth_discovery_v5_port: 9200
```

### reth_discovery_v5_port_ipv6

The UDP IPv6 port to use for devp2p peer discovery version 5. Not used unless `--addr` is IPv6, or `--discovery.addr.ipv6` is set.

#### Defaults

```YAML
reth_discovery_v5_port_ipv6: 9200
```

### reth_dns_retries

Amount of DNS resolution requests retries to perform when peering.

#### Defaults

```YAML
reth_dns_retries: 0
```

### reth_enable_discv5_discovery

Enable Discv5 discovery.

#### Defaults

```YAML
reth_enable_discv5_discovery: false
```

### reth_engine_accept_execution_requests_hash

Enables accepting requests hash instead of an array of requests in `engine_newPayloadV4`.

#### Defaults

```YAML
reth_engine_accept_execution_requests_hash: false
```

### reth_engine_cross_block_cache_size

Configure the size of cross-block cache in megabytes.

#### Defaults

```YAML
reth_engine_cross_block_cache_size: 4096
```

### reth_engine_disable_caching_and_prewarming

Disable cross-block caching and parallel prewarming. Note: --engine.caching-and-prewarming has no effect.

#### Defaults

```YAML
reth_engine_disable_caching_and_prewarming: false
```

### reth_engine_legacy_state_root

Enable legacy state root.

#### Defaults

```YAML
reth_engine_legacy_state_root: false
```

### reth_engine_max_proof_task_concurrency

Configure the maximum number of concurrent proof tasks.

#### Defaults

```YAML
reth_engine_max_proof_task_concurrency: 256
```

### reth_engine_memory_block_buffer_target

Configure the target number of blocks to keep in memory.

#### Defaults

```YAML
reth_engine_memory_block_buffer_target: 2
```

### reth_engine_persistence_threshold

Configure persistence threshold for engine experimental.

#### Defaults

```YAML
reth_engine_persistence_threshold: 2
```

### reth_engine_reserved_cpu_cores

Configure the number of reserved CPU cores for non-reth processes.

#### Defaults

```YAML
reth_engine_reserved_cpu_cores: 1
```

### reth_engine_state_provider_metrics

Enable state provider latency metrics. This allows the engine to collect and report stats about how long state provider calls took during execution, but this does introduce slight overhead to state provider calls.

#### Defaults

```YAML
reth_engine_state_provider_metrics: false
```

### reth_engine_state_root_task_compare_updates

Enable comparing trie updates from the state root task to the trie updates from the regular state root calculation.

#### Defaults

```YAML
reth_engine_state_root_task_compare_updates: false
```

### reth_extra_systemd_directives

A list of extra directives to add to the [Service] section (e.g., "Environment=RUST_LOG=info").

#### Defaults

```YAML
reth_extra_systemd_directives: []
```

### reth_full

Run full node. Only the most recent MINIMUM_PRUNING_DISTANCE block states are stored.

#### Defaults

```YAML
reth_full: false
```

### reth_general_owner

General owner for reth system files.

#### Defaults

```YAML
reth_general_owner: root
```

### reth_gpo_blocks

Number of recent blocks to check for gas price.

#### Defaults

```YAML
reth_gpo_blocks: 20
```

### reth_gpo_ignoreprice

Gas Price below which gpo will ignore transactions.

#### Defaults

```YAML
reth_gpo_ignoreprice: 2
```

### reth_gpo_maxprice

Maximum transaction priority fee(or gasprice before London Fork) to be recommended by gpo.

#### Defaults

```YAML
reth_gpo_maxprice: 500000000000
```

### reth_gpo_percentile

The percentile of gas prices to use for the estimate.

#### Defaults

```YAML
reth_gpo_percentile: 60
```

### reth_group

Group for running the reth node.

#### Defaults

```YAML
reth_group: reth
```

### reth_http_addr

Http server address to listen on.

#### Defaults

```YAML
reth_http_addr: 127.0.0.1
```

### reth_http_api

Rpc Modules to be configured for the HTTP server. Possible values: admin, debug, eth, net, trace, txpool, web3, rpc, reth, ots, flashbots, miner, mev. Comma-separated string e.g., "eth,net,web3".

#### Defaults

```YAML
reth_http_api: eth,net,web3,admin
```

### reth_http_corsdomain

Http Corsdomain to allow request from.

#### Defaults

```YAML
reth_http_corsdomain: '*'
```

### reth_http_port

Http server port to listen on.

#### Defaults

```YAML
reth_http_port: 8545
```

### reth_identity

Custom node identity.

#### Defaults

```YAML
reth_identity: reth/<VERSION>-<SHA>/<ARCH>
```

### reth_instance

Add a new instance of a node. Configures the ports of the node to avoid conflicts with the defaults. This is useful for running multiple nodes on the same machine. Max number of instances is 200. Changes to the following port numbers: - `DISCOVERY_PORT`: default + `instance` - 1 - `AUTH_PORT`: default + `instance` * 100 - 100 - `HTTP_RPC_PORT`: default - `instance` + 1 - `WS_RPC_PORT`: default + `instance` * 2 - 2 - `IPC_PATH`: default + `-instance`

#### Defaults

```YAML
reth_instance: 1
```

### reth_ipcdisable

Disable the IPC-RPC server.

#### Defaults

```YAML
reth_ipcdisable: false
```

### reth_ipcpath

Filename for IPC socket/pipe within the datadir.

#### Defaults

```YAML
reth_ipcpath: '{{ reth_dir_data }}/ipc'
```

### reth_jwt_secret_path

jwt token path for reth.

#### Defaults

```YAML
reth_jwt_secret_path: '{{ reth_dir_config }}/jwt.hex'
```

### reth_limit_nofile

Maximum number of open files for the Reth service.

### reth_log_file_directory

The path to put log files in.

#### Defaults

```YAML
reth_log_file_directory: <CACHE_DIR>/logs
```

### reth_log_file_filter

The filter to use for logs written to the log file.

#### Defaults

```YAML
reth_log_file_filter: debug
```

### reth_log_file_format

The format to use for logs written to the log file. Possible values: json, log-fmt, terminal.

#### Defaults

```YAML
reth_log_file_format: terminal
```

### reth_log_file_max_files

The maximum amount of log files that will be stored. If set to 0, background file logging is disabled.

#### Defaults

```YAML
reth_log_file_max_files: 5
```

### reth_log_file_max_size

The maximum size (in MB) of one log file.

#### Defaults

```YAML
reth_log_file_max_size: 200
```

### reth_log_journald

Write logs to journald.

#### Defaults

```YAML
reth_log_journald: false
```

### reth_log_journald_filter

The filter to use for logs written to journald.

#### Defaults

```YAML
reth_log_journald_filter: error
```

### reth_log_stdout_filter

The filter to use for logs written to stdout.

#### Defaults

```YAML
reth_log_stdout_filter: ''
```

### reth_log_stdout_format

The format to use for logs written to stdout. Possible values: json, log-fmt, terminal.

#### Defaults

```YAML
reth_log_stdout_format: terminal
```

### reth_max_inbound_peers

Maximum number of inbound requests.

#### Defaults

```YAML
reth_max_inbound_peers: 30
```

### reth_max_outbound_peers

Maximum number of outbound requests.

#### Defaults

```YAML
reth_max_outbound_peers: 100
```

### reth_max_pending_imports

Max number of transactions to import concurrently.

#### Defaults

```YAML
reth_max_pending_imports: 4096
```

### reth_max_seen_tx_history

Max number of seen transactions to remember per peer. Default is 320 transaction hashes.

#### Defaults

```YAML
reth_max_seen_tx_history: 320
```

### reth_max_tx_pending_fetch

Max capacity of cache of hashes for transactions pending fetch.

#### Defaults

```YAML
reth_max_tx_pending_fetch: 25600
```

### reth_max_tx_reqs

Max concurrent `GetPooledTransactions` requests.

#### Defaults

```YAML
reth_max_tx_reqs: 130
```

### reth_max_tx_reqs_peer

Max concurrent `GetPooledTransactions` requests per peer.

#### Defaults

```YAML
reth_max_tx_reqs_peer: 1
```

### reth_metrics_listen_addr

The metrics will be served at the given addr.

#### Defaults

```YAML
reth_metrics_listen_addr: 127.0.0.1
```

### reth_metrics_listen_port

The metrics will be served at the given port.

#### Defaults

```YAML
reth_metrics_listen_port: 9000
```

### reth_nat

NAT resolution method (any|none|upnp|publicip|extip:<IP>).

#### Defaults

```YAML
reth_nat: any
```

### reth_net_if_experimental

Name of network interface used to communicate with peers. If flag is set, but no value is passed, the default interface for docker `eth0` is tried.

#### Defaults

```YAML
reth_net_if_experimental: <IF_NAME>
```

### reth_no_persist_peers

Do not persist peers.

#### Defaults

```YAML
reth_no_persist_peers: false
```

### reth_p2p_secret_key

Secret key to use for this node. This will also deterministically set the peer ID. If not specified, it will be set in the data dir for the chain being used.

#### Defaults

```YAML
reth_p2p_secret_key: '{{ reth_dir_config }}/reth_p2p_secret'
```

### reth_peers_backoff_durations_high

High backoff duration for peer connections.

#### Defaults

```YAML
reth_peers_backoff_durations_high: 15m
```

### reth_peers_backoff_durations_low

Low backoff duration for peer connections.

#### Defaults

```YAML
reth_peers_backoff_durations_low: 30s
```

### reth_peers_backoff_durations_max

Maximum backoff duration for peer connections.

#### Defaults

```YAML
reth_peers_backoff_durations_max: 1h
```

### reth_peers_backoff_durations_medium

Medium backoff duration for peer connections.

#### Defaults

```YAML
reth_peers_backoff_durations_medium: 3m
```

### reth_peers_ban_duration

Duration for banning misbehaving peers.

#### Defaults

```YAML
reth_peers_ban_duration: 12h
```

### reth_peers_connection_info_max_concurrent_outbound_dials

Maximum concurrent outbound dials.

#### Defaults

```YAML
reth_peers_connection_info_max_concurrent_outbound_dials: 15
```

### reth_peers_connection_info_max_inbound

Maximum inbound peer connections. (Note: CLI --max-inbound-peers overrides this if set)

#### Defaults

```YAML
reth_peers_connection_info_max_inbound: 30
```

### reth_peers_connection_info_max_outbound

Maximum outbound peer connections. (Note: CLI --max-outbound-peers overrides this if set)

#### Defaults

```YAML
reth_peers_connection_info_max_outbound: 100
```

### reth_peers_file

The path to the known peers file. Connected peers are dumped to this file on nodes shutdown, and read on startup. Cannot be used with `reth_no_persist_peers`.

#### Defaults

```YAML
reth_peers_file: <FILE_PATH>
```

### reth_peers_incoming_ip_throttle_duration

Duration to throttle incoming connections from the same IP.

#### Defaults

```YAML
reth_peers_incoming_ip_throttle_duration: 30s
```

### reth_peers_max_backoff_count

Maximum backoff count for peer connections.

#### Defaults

```YAML
reth_peers_max_backoff_count: 5
```

### reth_peers_refill_slots_interval

Interval to refill peer slots.

#### Defaults

```YAML
reth_peers_refill_slots_interval: 5s
```

### reth_peers_reputation_weights_already_seen_transactions

Reputation weight for already seen transactions.

#### Defaults

```YAML
reth_peers_reputation_weights_already_seen_transactions: 0
```

### reth_peers_reputation_weights_bad_announcement

Reputation weight for a bad announcement.

#### Defaults

```YAML
reth_peers_reputation_weights_bad_announcement: -1024
```

### reth_peers_reputation_weights_bad_block

Reputation weight for a bad block.

#### Defaults

```YAML
reth_peers_reputation_weights_bad_block: -16384
```

### reth_peers_reputation_weights_bad_message

Reputation weight for a bad message.

#### Defaults

```YAML
reth_peers_reputation_weights_bad_message: -16384
```

### reth_peers_reputation_weights_bad_protocol

Reputation weight for a bad protocol.

#### Defaults

```YAML
reth_peers_reputation_weights_bad_protocol: -2147483648
```

### reth_peers_reputation_weights_bad_transactions

Reputation weight for bad transactions.

#### Defaults

```YAML
reth_peers_reputation_weights_bad_transactions: -16384
```

### reth_peers_reputation_weights_dropped

Reputation weight for a dropped peer.

#### Defaults

```YAML
reth_peers_reputation_weights_dropped: -4096
```

### reth_peers_reputation_weights_failed_to_connect

Reputation weight for a failed connection attempt.

#### Defaults

```YAML
reth_peers_reputation_weights_failed_to_connect: -25600
```

### reth_peers_reputation_weights_timeout

Reputation weight for a timeout.

#### Defaults

```YAML
reth_peers_reputation_weights_timeout: -4096
```

### reth_peers_trusted_nodes

List of trusted peer enode URLs.

#### Defaults

```YAML
reth_peers_trusted_nodes: []
```

### reth_peers_trusted_nodes_only

Connect only to trusted nodes.

#### Defaults

```YAML
reth_peers_trusted_nodes_only: false
```

### reth_pooled_tx_pack_soft_limit

Experimental, for usage in research. Sets the max accumulated byte size of transactions to request in one request. Since `RLPx` protocol version 68, the byte size of a transaction is shared as metadata in a transaction announcement. This allows a node to request a specific size response. By default, nodes request only 128 KiB worth of transactions, but should a peer request more, up to 2 MiB, a node will answer with more than 128 KiB. Default is 128 KiB.

#### Defaults

```YAML
reth_pooled_tx_pack_soft_limit: 131072
```

### reth_pooled_tx_response_soft_limit

Experimental, for usage in research. Sets the max accumulated byte size of transactions to pack in one response. Spec'd at 2MiB.

#### Defaults

```YAML
reth_pooled_tx_response_soft_limit: 2097152
```

### reth_port

Network listening port.

#### Defaults

```YAML
reth_port: 30303
```

### reth_prune_accounthistory_before

Prune account history before the specified block number. The specified block number is not pruned.

#### Defaults

```YAML
reth_prune_accounthistory_before: <BLOCK_NUMBER>
```

### reth_prune_accounthistory_distance

Prune account before the `head-N` block number. In other words, keep last N + 1 blocks.

#### Defaults

```YAML
reth_prune_accounthistory_distance: <BLOCKS>
```

### reth_prune_accounthistory_full

Prunes all account history.

#### Defaults

```YAML
reth_prune_accounthistory_full: false
```

### reth_prune_receipts_before

Prune receipts before the specified block number. The specified block number is not pruned.

#### Defaults

```YAML
reth_prune_receipts_before: <BLOCK_NUMBER>
```

### reth_prune_receipts_distance

Prune receipts before the `head-N` block number. In other words, keep last N + 1 blocks.

#### Defaults

```YAML
reth_prune_receipts_distance: <BLOCKS>
```

### reth_prune_receipts_full

Prunes all receipt data.

#### Defaults

```YAML
reth_prune_receipts_full: false
```

### reth_prune_receiptslogfilter

Configure receipts log filter. Format: <address>:<prune_mode>[,<address>:<prune_mode>...]. Where <prune_mode> can be 'full', 'distance:<blocks>', or 'before:<block_number>'.

#### Defaults

```YAML
reth_prune_receiptslogfilter: ''
```

### reth_prune_senderrecovery_before

Prune sender recovery data before the specified block number. The specified block number is not pruned.

#### Defaults

```YAML
reth_prune_senderrecovery_before: <BLOCK_NUMBER>
```

### reth_prune_senderrecovery_distance

Prune sender recovery data before the `head-N` block number. In other words, keep last N + 1 blocks.

#### Defaults

```YAML
reth_prune_senderrecovery_distance: <BLOCKS>
```

### reth_prune_senderrecovery_full

Prunes all sender recovery data.

#### Defaults

```YAML
reth_prune_senderrecovery_full: false
```

### reth_prune_storagehistory_before

Prune storage history before the specified block number. The specified block number is not pruned.

#### Defaults

```YAML
reth_prune_storagehistory_before: <BLOCK_NUMBER>
```

### reth_prune_storagehistory_distance

Prune storage history before the `head-N` block number. In other words, keep last N + 1 blocks.

#### Defaults

```YAML
reth_prune_storagehistory_distance: <BLOCKS>
```

### reth_prune_storagehistory_full

Prunes all storage history data.

#### Defaults

```YAML
reth_prune_storagehistory_full: false
```

### reth_prune_transactionlookup_before

Prune transaction lookup data before the specified block number. The specified block number is not pruned.

#### Defaults

```YAML
reth_prune_transactionlookup_before: <BLOCK_NUMBER>
```

### reth_prune_transactionlookup_distance

Prune transaction lookup data before the `head-N` block number. In other words, keep last N + 1 blocks.

#### Defaults

```YAML
reth_prune_transactionlookup_distance: <BLOCKS>
```

### reth_prune_transactionlookup_full

Prunes all transaction lookup data.

#### Defaults

```YAML
reth_prune_transactionlookup_full: false
```

### reth_quiet

Silence all log output. Overrides verbosity.

#### Defaults

```YAML
reth_quiet: false
```

### reth_reinstall

Force reinstall reth binary.

#### Defaults

```YAML
reth_reinstall: false
```

### reth_ress_enable

Enable support for `ress` subprotocol.

#### Defaults

```YAML
reth_ress_enable: false
```

### reth_ress_max_active_connections

The maximum number of active connections for `ress` subprotocol.

#### Defaults

```YAML
reth_ress_max_active_connections: 5
```

### reth_ress_max_witness_window

The maximum witness lookback window.

#### Defaults

```YAML
reth_ress_max_witness_window: 1024
```

### reth_ress_witness_cache_size

Witness cache size.

#### Defaults

```YAML
reth_ress_witness_cache_size: 10
```

### reth_ress_witness_max_parallel

The maximum number of witnesses to generate in parallel.

#### Defaults

```YAML
reth_ress_witness_max_parallel: 5
```

### reth_restart_policy

Restart policy for the Reth service.

### reth_restart_sec

Seconds to wait before restarting the service.

### reth_rpc_cache_max_blocks

Max number of blocks in RPC cache.

#### Defaults

```YAML
reth_rpc_cache_max_blocks: 5000
```

### reth_rpc_cache_max_concurrent_db_requests

Max number of concurrent database requests for RPC cache.

#### Defaults

```YAML
reth_rpc_cache_max_concurrent_db_requests: 512
```

### reth_rpc_cache_max_headers

Max number of headers in RPC cache.

#### Defaults

```YAML
reth_rpc_cache_max_headers: 1000
```

### reth_rpc_cache_max_receipts

Max number receipts in RPC cache.

#### Defaults

```YAML
reth_rpc_cache_max_receipts: 2000
```

### reth_rpc_eth_proof_window

The maximum proof window for historical proof generation. This value allows for generating historical proofs up to configured number of blocks from current tip (up to `tip - window`).

#### Defaults

```YAML
reth_rpc_eth_proof_window: 0
```

### reth_rpc_gascap

Maximum gas limit for `eth_call` and call tracing RPC methods.

#### Defaults

```YAML
reth_rpc_gascap: 50000000
```

### reth_rpc_jwtsecret

Hex encoded JWT secret to authenticate the regular RPC server(s), see `reth_http_api` and `reth_ws_api`. This is __not__ used for the authenticated engine-API RPC server, see `reth_authrpc_jwtsecret`.

#### Defaults

```YAML
reth_rpc_jwtsecret: ''
```

### reth_rpc_max_blocks_per_filter

Maximum number of blocks that could be scanned per filter request. (0 = entire chain).

#### Defaults

```YAML
reth_rpc_max_blocks_per_filter: 100000
```

### reth_rpc_max_connections

Maximum number of RPC server connections.

#### Defaults

```YAML
reth_rpc_max_connections: 500
```

### reth_rpc_max_logs_per_response

Maximum number of logs that can be returned in a single response. (0 = no limit).

#### Defaults

```YAML
reth_rpc_max_logs_per_response: 20000
```

### reth_rpc_max_request_size

Set the maximum RPC request payload size for both HTTP and WS in megabytes.

#### Defaults

```YAML
reth_rpc_max_request_size: 15
```

### reth_rpc_max_response_size

Set the maximum RPC response payload size for both HTTP and WS in megabytes.

#### Defaults

```YAML
reth_rpc_max_response_size: 160
```

### reth_rpc_max_simulate_blocks

Maximum number of blocks for `eth_simulateV1` call.

#### Defaults

```YAML
reth_rpc_max_simulate_blocks: 256
```

### reth_rpc_max_subscriptions_per_connection

Set the maximum concurrent subscriptions per connection.

#### Defaults

```YAML
reth_rpc_max_subscriptions_per_connection: 1024
```

### reth_rpc_max_trace_filter_blocks

Maximum number of blocks for `trace_filter` requests.

#### Defaults

```YAML
reth_rpc_max_trace_filter_blocks: 100
```

### reth_rpc_max_tracing_requests

Maximum number of concurrent tracing requests. By default this chooses a sensible value based on the number of available cores. Tracing requests are generally CPU bound. Choosing a value that is higher than the available CPU cores can have a negative impact on the performance.

#### Defaults

```YAML
reth_rpc_max_tracing_requests: '{{ ansible_processor_vcpus }}'
```

### reth_rpc_proof_permits

Maximum number of concurrent getproof requests.

#### Defaults

```YAML
reth_rpc_proof_permits: 25
```

### reth_rpc_txfeecap

Maximum eth transaction fee that can be sent via the RPC APIs (0 = no cap).

#### Defaults

```YAML
reth_rpc_txfeecap: 1.0
```

### reth_sessions_initial_internal_request_timeout_nanos

Nanoseconds for initial internal request timeout.

#### Defaults

```YAML
reth_sessions_initial_internal_request_timeout_nanos: 0
```

### reth_sessions_initial_internal_request_timeout_secs

Seconds for initial internal request timeout.

#### Defaults

```YAML
reth_sessions_initial_internal_request_timeout_secs: 20
```

### reth_sessions_pending_session_timeout_nanos

Nanoseconds for pending session timeout.

#### Defaults

```YAML
reth_sessions_pending_session_timeout_nanos: 0
```

### reth_sessions_pending_session_timeout_secs

Seconds for pending session timeout.

#### Defaults

```YAML
reth_sessions_pending_session_timeout_secs: 20
```

### reth_sessions_protocol_breach_request_timeout_nanos

Nanoseconds for protocol breach request timeout.

#### Defaults

```YAML
reth_sessions_protocol_breach_request_timeout_nanos: 0
```

### reth_sessions_protocol_breach_request_timeout_secs

Seconds for protocol breach request timeout.

#### Defaults

```YAML
reth_sessions_protocol_breach_request_timeout_secs: 120
```

### reth_sessions_session_command_buffer

Buffer size for session commands.

#### Defaults

```YAML
reth_sessions_session_command_buffer: 32
```

### reth_sessions_session_event_buffer

Buffer size for session events.

#### Defaults

```YAML
reth_sessions_session_event_buffer: 260
```

### reth_stages_account_hashing_clean_threshold

Clean threshold for the account hashing stage.

#### Defaults

```YAML
reth_stages_account_hashing_clean_threshold: 500000
```

### reth_stages_account_hashing_commit_threshold

Commit threshold for the account hashing stage.

#### Defaults

```YAML
reth_stages_account_hashing_commit_threshold: 100000
```

### reth_stages_bodies_downloader_max_buffered_blocks_size_bytes

Maximum buffered blocks size in bytes for body downloads.

#### Defaults

```YAML
reth_stages_bodies_downloader_max_buffered_blocks_size_bytes: 2147483648
```

### reth_stages_bodies_downloader_max_concurrent_requests

Maximum concurrent download requests for bodies.

#### Defaults

```YAML
reth_stages_bodies_downloader_max_concurrent_requests: 100
```

### reth_stages_bodies_downloader_min_concurrent_requests

Minimum concurrent download requests for bodies.

#### Defaults

```YAML
reth_stages_bodies_downloader_min_concurrent_requests: 5
```

### reth_stages_bodies_downloader_request_limit

Request limit for body downloads.

#### Defaults

```YAML
reth_stages_bodies_downloader_request_limit: 200
```

### reth_stages_bodies_downloader_stream_batch_size

Stream batch size for body downloads.

#### Defaults

```YAML
reth_stages_bodies_downloader_stream_batch_size: 1000
```

### reth_stages_etl_file_size

File size for the ETL stage.

#### Defaults

```YAML
reth_stages_etl_file_size: 524288000
```

### reth_stages_execution_max_blocks

Maximum blocks for the execution stage.

#### Defaults

```YAML
reth_stages_execution_max_blocks: 500000
```

### reth_stages_execution_max_changes

Maximum changes for the execution stage.

#### Defaults

```YAML
reth_stages_execution_max_changes: 5000000
```

### reth_stages_execution_max_cumulative_gas

Maximum cumulative gas for the execution stage.

#### Defaults

```YAML
reth_stages_execution_max_cumulative_gas: 1500000000000
```

### reth_stages_execution_max_duration

Maximum duration for the execution stage.

#### Defaults

```YAML
reth_stages_execution_max_duration: 10m
```

### reth_stages_headers_commit_threshold

Commit threshold for the headers stage.

#### Defaults

```YAML
reth_stages_headers_commit_threshold: 10000
```

### reth_stages_headers_downloader_max_buffered_responses

Maximum buffered responses for header downloads.

#### Defaults

```YAML
reth_stages_headers_downloader_max_buffered_responses: 100
```

### reth_stages_headers_downloader_max_concurrent_requests

Maximum concurrent download requests for headers.

#### Defaults

```YAML
reth_stages_headers_downloader_max_concurrent_requests: 100
```

### reth_stages_headers_downloader_min_concurrent_requests

Minimum concurrent download requests for headers.

#### Defaults

```YAML
reth_stages_headers_downloader_min_concurrent_requests: 5
```

### reth_stages_headers_downloader_request_limit

Request limit for header downloads.

#### Defaults

```YAML
reth_stages_headers_downloader_request_limit: 1000
```

### reth_stages_index_account_history_commit_threshold

Commit threshold for the index account history stage.

#### Defaults

```YAML
reth_stages_index_account_history_commit_threshold: 100000
```

### reth_stages_index_storage_history_commit_threshold

Commit threshold for the index storage history stage.

#### Defaults

```YAML
reth_stages_index_storage_history_commit_threshold: 100000
```

### reth_stages_merkle_clean_threshold

Clean threshold for the Merkle stage.

#### Defaults

```YAML
reth_stages_merkle_clean_threshold: 5000
```

### reth_stages_prune_commit_threshold

Commit threshold for the prune stage.

#### Defaults

```YAML
reth_stages_prune_commit_threshold: 1000000
```

### reth_stages_sender_recovery_commit_threshold

Commit threshold for the sender recovery stage.

#### Defaults

```YAML
reth_stages_sender_recovery_commit_threshold: 5000000
```

### reth_stages_storage_hashing_clean_threshold

Clean threshold for the storage hashing stage.

#### Defaults

```YAML
reth_stages_storage_hashing_clean_threshold: 500000
```

### reth_stages_storage_hashing_commit_threshold

Commit threshold for the storage hashing stage.

#### Defaults

```YAML
reth_stages_storage_hashing_commit_threshold: 100000
```

### reth_stages_transaction_lookup_chunk_size

Chunk size for the transaction lookup stage.

#### Defaults

```YAML
reth_stages_transaction_lookup_chunk_size: 5000000
```

### reth_stop_timeout_sec

Timeout in seconds when stopping the service.

### reth_systemd_limit_nofile

#### Defaults

```YAML
reth_systemd_limit_nofile: 65536
```

### reth_systemd_restart_policy

#### Defaults

```YAML
reth_systemd_restart_policy: always
```

### reth_systemd_restart_sec

#### Defaults

```YAML
reth_systemd_restart_sec: 5
```

### reth_systemd_service_name

Systemd service name for reth.

#### Defaults

```YAML
reth_systemd_service_name: reth
```

### reth_systemd_stop_timeout_sec

#### Defaults

```YAML
reth_systemd_stop_timeout_sec: 300
```

### reth_trusted_only

Connect to or accept from trusted peers only.

#### Defaults

```YAML
reth_trusted_only: false
```

### reth_trusted_peers

Comma separated enode URLs of trusted peers for P2P connections. Example: "enode://abcd@192.168.0.1:30303,enode://efgh@192.168.0.2:30303"

#### Defaults

```YAML
reth_trusted_peers: ''
```

### reth_tx_propagation_policy

Transaction Propagation Policy. The policy determines which peers transactions are gossiped to.

#### Defaults

```YAML
reth_tx_propagation_policy: All
```

### reth_txpool_additional_validation_tasks

Number of additional transaction validation tasks to spawn.

#### Defaults

```YAML
reth_txpool_additional_validation_tasks: 1
```

### reth_txpool_basefee_max_count

Max number of transaction in the basefee sub-pool.

#### Defaults

```YAML
reth_txpool_basefee_max_count: 10000
```

### reth_txpool_basefee_max_size

Max size of the basefee sub-pool in megabytes.

#### Defaults

```YAML
reth_txpool_basefee_max_size: 20
```

### reth_txpool_blob_cache_size

Max number of entries for the in memory cache of the blob store.

#### Defaults

```YAML
reth_txpool_blob_cache_size: <COUNT>
```

### reth_txpool_blobpool_max_count

Max number of transaction in the blobpool.

#### Defaults

```YAML
reth_txpool_blobpool_max_count: 10000
```

### reth_txpool_blobpool_max_size

Max size of the blobpool in megabytes.

#### Defaults

```YAML
reth_txpool_blobpool_max_size: 20
```

### reth_txpool_disable_transactions_backup

Disables transaction backup to disk on node shutdown.

#### Defaults

```YAML
reth_txpool_disable_transactions_backup: false
```

### reth_txpool_gas_limit

The default enforced gas limit for transactions entering the pool.

#### Defaults

```YAML
reth_txpool_gas_limit: 30000000
```

### reth_txpool_lifetime

Maximum amount of time non-executable transaction are queued (e.g., "10800s", "3h").

#### Defaults

```YAML
reth_txpool_lifetime: '10800'
```

### reth_txpool_locals

Flag to allow certain addresses as local. Comma-separated list of addresses.

#### Defaults

```YAML
reth_txpool_locals: ''
```

### reth_txpool_max_account_slots

Max number of executable transaction slots guaranteed per account.

#### Defaults

```YAML
reth_txpool_max_account_slots: 16
```

### reth_txpool_max_cached_entries

The maximum number of blobs to keep in the in memory blob cache.

#### Defaults

```YAML
reth_txpool_max_cached_entries: 100
```

### reth_txpool_max_new_pending_txs_notifications

How many new pending transactions to buffer and send to in progress pending transaction iterators.

#### Defaults

```YAML
reth_txpool_max_new_pending_txs_notifications: 200
```

### reth_txpool_max_new_txns

Maximum number of new transactions to buffer.

#### Defaults

```YAML
reth_txpool_max_new_txns: 1024
```

### reth_txpool_max_pending_txns

Maximum number of pending transactions from the network to buffer.

#### Defaults

```YAML
reth_txpool_max_pending_txns: 2048
```

### reth_txpool_max_tx_input_bytes

Max size in bytes of a single transaction allowed to enter the pool.

#### Defaults

```YAML
reth_txpool_max_tx_input_bytes: 131072
```

### reth_txpool_minimal_protocol_fee

Minimum base fee required by the protocol.

#### Defaults

```YAML
reth_txpool_minimal_protocol_fee: 7
```

### reth_txpool_no_local_transactions_propagation

Flag to toggle local transaction propagation.

#### Defaults

```YAML
reth_txpool_no_local_transactions_propagation: false
```

### reth_txpool_nolocals

Flag to disable local transaction exemptions.

#### Defaults

```YAML
reth_txpool_nolocals: false
```

### reth_txpool_pending_max_count

Max number of transaction in the pending sub-pool.

#### Defaults

```YAML
reth_txpool_pending_max_count: 10000
```

### reth_txpool_pending_max_size

Max size of the pending sub-pool in megabytes.

#### Defaults

```YAML
reth_txpool_pending_max_size: 20
```

### reth_txpool_pricebump

Price bump (in %) for the transaction pool underpriced check.

#### Defaults

```YAML
reth_txpool_pricebump: 10
```

### reth_txpool_queued_max_count

Max number of transaction in the queued sub-pool.

#### Defaults

```YAML
reth_txpool_queued_max_count: 10000
```

### reth_txpool_queued_max_size

Max size of the queued sub-pool in megabytes.

#### Defaults

```YAML
reth_txpool_queued_max_size: 20
```

### reth_txpool_transactions_backup

Path to store the local transaction backup at, to survive node restarts.

#### Defaults

```YAML
reth_txpool_transactions_backup: '{{ reth_dir_data }}'
```

### reth_user

Username for the reth node.

#### Defaults

```YAML
reth_user: reth
```

### reth_verbosity

Set the minimum log level. 0: Default (Info if not quiet, otherwise based on RUST_LOG or other settings) 1: Errors (-v) 2: Warnings (-vv) 3: Info (-vvv) 4: Debug (-vvvv) 5: Traces (-vvvvv, warning: very verbose!)

#### Defaults

```YAML
reth_verbosity: vvvv
```

### reth_with_unused_ports

Sets all ports to unused, allowing the OS to choose random unused ports when sockets are bound. Mutually exclusive with `reth_instance`.

#### Defaults

```YAML
reth_with_unused_ports: false
```

### reth_ws_addr

Ws server address to listen on.

#### Defaults

```YAML
reth_ws_addr: 127.0.0.1
```

### reth_ws_api

Rpc Modules to be configured for the WS server. Possible values: admin, debug, eth, net, trace, txpool, web3, rpc, reth, ots, flashbots, miner, mev. Comma-separated string e.g., "eth,net,web3".

#### Defaults

```YAML
reth_ws_api: ''
```

### reth_ws_origins

Origins from which to accept `WebSocket` requests. Comma-separated string e.g., "http://localhost:3000,https://example.com".

#### Defaults

```YAML
reth_ws_origins: '*'
```

### reth_ws_port

Ws server port to listen on.

#### Defaults

```YAML
reth_ws_port: 8546
```

## Tags

**_reth-config_**

**_reth-install_**

**_reth-prepare_**

## Dependencies

None.
