FROM quay.io/redhat-services-prod/cost-mgmt-dev-tenant/ubi-trino:470-009

# Override ENTRYPOINT to prevent immediate execution of the base image's CMD
ENTRYPOINT ["/bin/bash", "-c"]

# Copy your configuration and data
COPY ./etc/config.properties /etc/trino/config.properties
COPY ./etc/jvm.config /etc/trino/jvm.config
COPY ./etc/log.properties /etc/trino/log.properties
COPY ./etc/catalog/hive.properties /etc/trino/catalog/hive.properties
COPY ./etc/catalog/glue.properties /etc/trino/catalog/glue.properties
COPY ./etc/catalog/postgres.properties /etc/trino/catalog/postgres.properties
COPY ./data /data/trino/data
COPY ./logs /data/trino/logs

# After files are copied, run the original CMD from the base image
CMD ["/usr/lib/trino/run-trino"]
