# opensearch

Create opensearch password:
```bash
export OPENSEARCH_INITIAL_ADMIN_PASSWORD=$(openssl rand -hex 64)
echo $OPENSEARCH_INITIAL_ADMIN_PASSWORD
```

Start OpenSeach:
```bash
docker-compose up -d
```

CPU: 4 \
RAM: 8 GB \
Storage: 100 GB
