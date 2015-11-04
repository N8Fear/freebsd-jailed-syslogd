Role Name
=========

This role provides a jailed syslogd server. Nothing more.

To see this role in a wider perspective, have a look at [this project of mine](https://github.com/JoergFiedler/freebsd-ansible-demo).

Requirements
------------

This role is intent to be used with a fresh FreeBSD 10.2 installation. There is a Vagrant Box with providers for VirtualBox and EC2 you may use.

You will find a sample project which uses this role [here](https://github.com/JoergFiedler/freebsd-ansible-demo).

Role Variables
--------------

##### js_jail_name

The name for the jail. Local part of the hostname. Default: `''`.

##### js_jail_domain

The domain this jail belongs to. Domain part of the hostname. Default: `'darkcity'`.

##### js_jail_net_if

The interface to which the jail's ip address is added. Default: `'lo0'`.

##### js_jail_net_ip

The jail's ip address. Default: `''`.

##### js_jail_net_net

The network mask the jail accepts syslog messages from. Default: `'{{ js_jail_net_ip }}/24'`.

##### js_ioc_jails_dir

The directory iocage creates jails in. Default: `'/iocage/jails'`.

##### js_ssmtp_forward_address

System mails are forwarded to this address. See [ssmtp man page](https://www.freebsd.org/cgi/man.cgi?query=ssmtp&apropos=0&sektion=0&manpath=FreeBSD+10.2-RELEASE+and+Ports&arch=default&format=html) for further information.

Default: `'freebsd-ansible-demo@maildrop.cc'`.

This behaviour is only active, if the variable 'ssmtp' is set to any value.

##### js_ssmtp_forward_mailhub

System mails are forwarded using this mail relay. See [ssmtp man page](https://www.freebsd.org/cgi/man.cgi?query=ssmtp&apropos=0&sektion=0&manpath=FreeBSD+10.2-RELEASE+and+Ports&arch=default&format=html) for further information.

Default: `'mail.maildrop.cc'`.

This behaviour is only active, if the variable 'ssmtp' is set to any value.

Dependencies
------------

- JoergFiedler.freebsd-jail-host

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

If you like it or do have ideas to improve this project, please open an issue on Github. Thanks.
