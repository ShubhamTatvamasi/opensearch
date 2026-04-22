# opensearch

Add Helm repo:
```bash
helm repo add opensearch https://opensearch-project.github.io/helm-charts
```

Install opensearch:
```bash
helm upgrade -i opensearch opensearch/opensearch \
  --version 3.6.0 \
  --namespace opensearch \
  --create-namespace \
  --set protocol=http \
  --set singleNode=true \
  --set-string 'extraEnvs[0].name=OPENSEARCH_INITIAL_ADMIN_PASSWORD' \
  --set-string 'extraEnvs[0].value=StrongPassword123!' \
  --set config.'opensearch.yml'."plugins.security.disabled"=true
```

Install opensearch-dashboards:
```bash
helm upgrade -i opensearch-dashboards opensearch/opensearch-dashboards \
  --version 3.6.0 \
  --namespace opensearch \
  --create-namespace \
  --set service.type=LoadBalancer \
  --set opensearchHosts="http://opensearch-cluster-master:9200"
```

ID and password: `admin` / `StrongPassword123!`

---

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
