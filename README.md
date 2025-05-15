# ansible_reth

Ansible role for deploying Reth Ethereum Execution layer node

## Auto-generated

- [Defaults](#default-vars)
  - [reth_authrpc_addr](#reth_authrpc_addr)
  - [reth_authrpc_port](#reth_authrpc_port)
  - [reth_binary_download_url](#reth_binary_download_url)
  - [reth_binary_path](#reth_binary_path)
  - [reth_chain](#reth_chain)
  - [reth_cli_custom_flags](#reth_cli_custom_flags)
  - [reth_cli_custom_options](#reth_cli_custom_options)
  - [reth_cli_default_flags](#reth_cli_default_flags)
  - [reth_cli_default_options](#reth_cli_default_options)
  - [reth_config_file](#reth_config_file)
  - [reth_dir_base](#reth_dir_base)
  - [reth_dir_binary](#reth_dir_binary)
  - [reth_dir_config](#reth_dir_config)
  - [reth_dir_data](#reth_dir_data)
  - [reth_dir_log](#reth_dir_log)
  - [reth_dir_systemd](#reth_dir_systemd)
  - [reth_extra_systemd_directives](#reth_extra_systemd_directives)
  - [reth_general_owner](#reth_general_owner)
  - [reth_group](#reth_group)
  - [reth_http_addr](#reth_http_addr)
  - [reth_http_api](#reth_http_api)
  - [reth_http_corsdomain](#reth_http_corsdomain)
  - [reth_http_port](#reth_http_port)
  - [reth_jwt_secret_path](#reth_jwt_secret_path)
  - [reth_limit_nofile](#reth_limit_nofile)
  - [reth_metrics_listen_addr](#reth_metrics_listen_addr)
  - [reth_metrics_listen_port](#reth_metrics_listen_port)
  - [reth_peers_backoff_durations_high](#reth_peers_backoff_durations_high)
  - [reth_peers_backoff_durations_low](#reth_peers_backoff_durations_low)
  - [reth_peers_backoff_durations_max](#reth_peers_backoff_durations_max)
  - [reth_peers_backoff_durations_medium](#reth_peers_backoff_durations_medium)
  - [reth_peers_ban_duration](#reth_peers_ban_duration)
  - [reth_peers_connection_info_max_concurrent_outbound_dials](#reth_peers_connection_info_max_concurrent_outbound_dials)
  - [reth_peers_connection_info_max_inbound](#reth_peers_connection_info_max_inbound)
  - [reth_peers_connection_info_max_outbound](#reth_peers_connection_info_max_outbound)
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
  - [reth_prune_block_interval](#reth_prune_block_interval)
  - [reth_prune_segments_account_history_distance](#reth_prune_segments_account_history_distance)
  - [reth_prune_segments_receipts_before](#reth_prune_segments_receipts_before)
  - [reth_prune_segments_sender_recovery_distance](#reth_prune_segments_sender_recovery_distance)
  - [reth_prune_segments_storage_history_distance](#reth_prune_segments_storage_history_distance)
  - [reth_prune_segments_transaction_lookup](#reth_prune_segments_transaction_lookup)
  - [reth_reinstall](#reth_reinstall)
  - [reth_restart_policy](#reth_restart_policy)
  - [reth_restart_sec](#reth_restart_sec)
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
  - [reth_user](#reth_user)
  - [reth_verbosity](#reth_verbosity)
- [Tags](#tags)

- [Dependencies](#dependencies)

---

## Defaults

### reth_authrpc_addr

Auth server address to listen on.

#### Defaults

```YAML
reth_authrpc_addr: 127.0.0.1
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
reth_binary_download_url:
  https://github.com/paradigmxyz/reth/releases/download/v1.3.12/reth-v1.3.12-x86_64-unknown-linux-gnu.tar.gz
```

### reth_binary_path

Path the reth binary.

#### Defaults

```YAML
reth_binary_path: '{{ reth_dir_binary }}/reth'
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
  - --authrpc.jwtsecret={{ reth_jwt_secret_path }}
  - --log.file.directory={{ reth_dir_log }}
```

### reth_config_file

The path to the TOML configuration file to use.

#### Defaults

```YAML
reth_config_file: '{{ reth_dir_config }}/config.toml'
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

### reth_extra_systemd_directives

A list of extra directives to add to the [Service] section (e.g., "Environment=RUST_LOG=info").

#### Defaults

```YAML
reth_extra_systemd_directives: []
```

### reth_general_owner

General owner for reth system files.

#### Defaults

```YAML
reth_general_owner: root
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

### reth_jwt_secret_path

jwt token path for reth.

#### Defaults

```YAML
reth_jwt_secret_path: '{{ reth_dir_config }}/jwt.hex'
```

### reth_limit_nofile

Maximum number of open files for the Reth service.

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

### reth_prune_block_interval

Minimum pruning interval measured in blocks.

#### Defaults

```YAML
reth_prune_block_interval: 5
```

### reth_prune_segments_account_history_distance

Prune all historical account states before the block `head - <distance>`.

#### Defaults

```YAML
reth_prune_segments_account_history_distance: 100000
```

### reth_prune_segments_receipts_before

Prune all receipts from transactions before this block number, i.e. keep receipts from this block number onwards. This setting overrides `receipts_log_filter`.

#### Defaults

```YAML
reth_prune_segments_receipts_before: 1920000
```

### reth_prune_segments_sender_recovery_distance

Prune all transaction senders before the block `head - <distance>`, i.e. keep transaction senders for the last `<distance> + 1` blocks.

#### Defaults

```YAML
reth_prune_segments_sender_recovery_distance: 100000
```

### reth_prune_segments_storage_history_distance

Prune all historical storage states before the block `head - <distance>`.

#### Defaults

```YAML
reth_prune_segments_storage_history_distance: 100000
```

### reth_prune_segments_transaction_lookup

Transaction Lookup pruning configuration. "full" indicates pruning all TxNumber => TxHash mappings.

#### Defaults

```YAML
reth_prune_segments_transaction_lookup: full
```

### reth_reinstall

Force reinstall reth binary.

#### Defaults

```YAML
reth_reinstall: false
```

### reth_restart_policy

Restart policy for the Reth service.

### reth_restart_sec

Seconds to wait before restarting the service.

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
reth_verbosity: vv
```

## Tags

**_reth-config_**

**_reth-install_**

**_reth-prepare_**

## Dependencies

None.
