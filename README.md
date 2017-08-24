Steps to reproduce r10k single module update behavior:

    r10k deploy environment production -p -c r10k.yaml
    rm -r /tmp/r10k/code/enviromments/production/modules/concat
    r10k deploy module stdlib -e production -v info -c r10k.yaml # Updates stdlib
    ! test -e /tmp/r10k/code/environments/production/modules/concat && echo 'module "concat" does not exist

The initial full environment deployment seems to be necessary.
