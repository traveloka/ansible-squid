# shared/squid3 #

Ensures squid3 is installed and configured.
Customized from squid role created by Kevin Brebanov on ansible-galaxy.

## Requirements ##

Requires Ansible 2.0.

## Role Variables ##

### Defaults ###

    - name: squid_ssl_ports
      desc: list of SSL ports allowed to use CONNECT method.
      value:
        - 443
        - 1025-65535

    - name: squid_always_directs
      desc: List of always_direct options (keys: type, acl_name)
      value: []

    - name: squid_cache_peers
      desc: List of cache peers (keys: hostname, type, http_port, icp_port, options<list>)
      value: []

    - name: squid_dns_v4_first
      desc: This option reverses the order of preference to make Squid contact dual-stack websites over IPv4 first
      value: "off"

    - name: squid_forwarded_for
      desc: Set X-Forwarded-For header in HTTP requests
      value: "delete"

    - name: squid_http_port
      desc: The port where Squid will listen for HTTP requests
      value: 3128

    - squid_never_directs
      desc: List of never_direct options (keys: type, acl_name)
      value: []

    - name: squid_proxy_only
      desc: If true, disables caching
      value: true

    - name: squid_tcp_outgoing_address
      desc: Map requests to different outgoing IP address 
      value: ''

### Vars ###

    - name: squid_packages
      desc: List of squid packages to install
      value: squid3

    - name: squid_etc_dir
      desc: path to squid configuration directory
      value: /etc/squid3

    - name: squid_service_name
      desc: Name of squid service
      value: squid3


## Dependencies ##

None.

## Example Playbook ##

    - hosts: all
      roles:
        - role: shared/squid

    - hosts: all
      roles:
        - role: shared/squid

