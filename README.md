# Sample config for ansible-oracle

checkout with --recursive, as ansible-oracle is added as a submodule

ansible-oracle misses a 19.3.0.0 template for netca, as of now. there is merge request to add, until then:

    cp ./ansible-oracle/roles/oradb-manage-db/templates/netca.rsp.18.3.0.0.j2 ./ansible-oracle/roles/oradb-manage-db/templates/netca.rsp.19.3.0.0.j2


* network config (sqlnet, listener, tnsnames)
