openresty-docker
================
Based on tenstartups/openresty with some lua libraries (lua-filesystem, lua-socket) added. 

Example run:

    nginx_confdir=/etc/nginx
    ssl_crt=some.crt
    ssl_key=some.key
    docker run --name openresty \
    --link redis:redis \
    -v `pwd`/nginx.conf:$nginx_confdir/nginx.conf:ro \
    -v `pwd`/$ssl_crt:$nginx_confdir/$ssl_crt \
    -v `pwd`/$ssl_key:$nginx_confdir/$ssl_key \
    -d jamesyale/openresty

