OpenStack sahara
##############
:tags: openstack, sahara, cloud, ansible
:category: \*nix

Role to install sahara api and sahara engin.

This role will install the following:
    * sahara-api
    * sahara-engine

.. code-block:: yaml

    - name: Install sahara server
      hosts: sahara_all
      user: root
      roles:
        - { role: "os_sahara", tags: [ "os-sahara" ] }
      vars:
        external_lb_vip_address: 172.16.24.1
        internal_lb_vip_address: 192.168.0.1
        galera_address: "{{ internal_lb_vip_address }}"
        keystone_admin_user_name: admin
        keystone_admin_tenant_name: admin
