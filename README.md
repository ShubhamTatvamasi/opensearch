# opensearch

Install pwgen for password generation:
```bash
sudo apt install pwgen
```

Create opensearch password:
```bash
echo "OPENSEARCH_INITIAL_ADMIN_PASSWORD=$(pwgen -y 20 1)" > .env
```

Start OpenSeach:
```bash
docker-compose up -d
```

CPU: 4 \
RAM: 8 GB \
Storage: 100 GB
