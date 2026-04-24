# query

Get inside opensearch pod:
```bash
kubectl -n opensearch \
  exec -it opensearch-cluster-master-0 -- bash
```

Check indices:
```bash
curl http://opensearch-cluster-master.opensearch:9200/_cat/indices?v
```
