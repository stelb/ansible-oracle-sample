# Sample config for ansible-oracle

checkout with --recursive, as ansible-oracle is added as a submodule

ansible-oracle misses a 19.3.0.0 template for netca, as of now. (oravirt/ansible-oracle#200) until this is fixed:

    cp ./ansible-oracle/roles/oradb-manage-db/templates/netca.rsp.18.3.0.0.j2 ./ansible-oracle/roles/oradb-manage-db/templates/netca.rsp.19.3.0.0.j2

I use a nfs mount for /u01/stage, use whatever you like. (copying huge files with ansible is a pain in the ass..)

Some special stuff:
* network config (sqlnet, listener, tnsnames)
* apply RU 19.9 patch

## Why not ansible-oracle nfs mount?

Well I tried, but some directories are created in /u01/stage before mounting and then needed after mounting and missing. Maybe I misunderstood/misconfigured something or it's a broken.
