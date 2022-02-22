system_filesystem
=========

This role allows you to use the community.general.filesystem module to create, resize or remove filesystems.

Requirements
------------

ansible >= 2.10

Role Variables
--------------

```yml
system_filesystem:
  first_entry:
    dev: ...
    force: ...
    fstype: ...
    opts: ...
    resizefs: ...
    state: ...
  second_entry:
    .
    .
    .
  .
  .
  .
```

Dependencies
------------

None

Example Playbook
----------------

#### Create a filesystem:
```yml
- hosts: servers
  vars:
    system_filesystem:
      sbd1:
        dev: /dev/sdb1
        fstype: xfs
  roles:
    - turcumihaiioan.system_filesystem
```

#### Resize a filesystem:
```yml
- hosts: servers
  vars:
    system_filesystem:
      sbd2:
        dev: /dev/sdb2
        resizefs: true
  roles:
    - turcumihaiioan.system_filesystem
```

#### Remove a filesystem:
```yml
- hosts: servers
  vars:
    system_filesystem:
      sbd3:
        dev: /dev/sdb3
        state: absent
  roles:
    - turcumihaiioan.system_filesystem
```

License
-------

GPL-3.0-only

Author Information
------------------

Role created by Turcu Mihai Ioan

