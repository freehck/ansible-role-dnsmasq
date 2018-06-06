dnsmasq
=========

This role aims to create a simple DNS server with A-records resolving.


Role Variables
--------------

dnsmasq.address: ip address where dnsmasq will listens
dnsmasq.domain: local domain
dnsmasq.table: file to store A-records, similar to /etc/hosts

dns.records: list of A-records (ip and names)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: dnsmasq.server.local
      become: yes
      become_user: root
      roles:
        - role: dnsmasq
          dnsmasq:
            address: 0.0.0.0
            domain: crptech.local
            table: /etc/my_hosts
          dns:
            records:
            # hw-servers
              - ip: 10.100.0.1
                names: [ srv01, srv01.server.local ]
              - ip: 10.100.0.2
				names: [ srv02, srv02.server.local ]
			  


License
-------

GPLv3

Author Information
------------------

This role was written by Dmitrii Kashin aka freehck
