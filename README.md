NSCD
=========


Install the Name Service Cache Daemon.

Requirements
------------

None.


Role Variables
--------------

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `nscd_logfile` | `/var/log/nscd.log` | Log file location. |
| `nscd_threads` | `4` | Number of threads that start and wait for requests. |
| `nscd_max_threads` | `32` | Max number of threads. |
| `nscd_server_user` | `nscd` | User account that runs `nscd`. |
| `nscd_stat_user` |   `somebody` | User who is allowed to request statistics. |
| `nscd_debug_level` | `0` | Debug level (rang. 0-10). |
| `nscd_reload_count` |    `5` | Number of times a cached entry is reloaded before it is removed. |
| `nscd_paranoia` | `no` | Whether or not to restart `nscd` periodically. |
| `nscd_restart_interval` | `3600` | Interval in seconds to restart `nscd` if `nscd_paranoia` is set to `yes`. |
| `nscd_services` | `[see /defaults/main.yml]` | Dict of valid service groups and the settings for each group. Valid services are `passwd, group, hosts, services or netgroup.` |

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: samdoran.nscd
           vars:
             nscd_debug_level: 1
             nscd_paranoia: 'yes'

License
-------

Apache 2.0
