theforeman.operations.proxy_certs_generate
==========================================

Run `foreman-proxy-certs-generate`

Role Variables
--------------

Required:

- `proxy_certs_generate_target`: The FQDN of the machine the certificates should be generated for.

Optional:

- `proxy_certs_generate_certs_tar`: Absolute path to the generate certificate tarball (default: `/root/{{ proxy_certs_generate_target }}.tar.gz`).
- `proxy_certs_generate_options`: Array of options to pass to `foreman-proxy-certs-generate`
- `proxy_certs_generate_command`: command to run, can be used by derivative projects to specify a branded command

Example Playbooks
-----------------

Run the proxy_certs_generate setting the initial admin password:

```yaml
- hosts: target-host
  roles:
    - role: theforeman.operations.proxy_certs_generate
      vars:
        proxy_certs_generate_options:
          - '--foreman-initial-admin-password changeme'
```
