ARG KONG_BASE=kong:latest

#FROM ${KONG_BASE} AS build

#ARG PLUGINS
#ENV INJECTED_PLUGINS=${PLUGINS}

#ARG TEMPLATE=empty_file
#ENV TEMPLATE=${TEMPLATE}

#ARG ROCKS_DIR=empty_file
#ENV ROCKS_DIR=${ROCKS_DIR}

#ARG KONG_LICENSE_DATA
#ENV KONG_LICENSE_DATA=${KONG_LICENSE_DATA}

#COPY $TEMPLATE /plugins/custom_nginx.conf
#COPY $ROCKS_DIR /rocks-server
#COPY packer.lua /packer.lua

#RUN /usr/local/openresty/luajit/bin/luajit /packer.lua -- "$INJECTED_PLUGINS"



FROM ${KONG_BASE}

#COPY --from=build /plugins /plugins
#RUN /plugins/install_plugins.sh

# add url-regex-rewriter plugin    
# Ethan
COPY url-regex-rewriter /gino/kong/plugins/url-regex-rewriter
ENV KONG_LUA_PACKAGE_PATH=/gino/?.lua
ENV KONG_PLUGINS=bundled,url-regex-rewriter

