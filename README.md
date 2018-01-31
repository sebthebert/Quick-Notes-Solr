# Quick Notes about Solr

Run Solr Docker Image:
```shell
docker pull solr:7.2-alpine
docker run --name solr -d -p 8983:8983 -t solr:7.2-alpine
```

Create a new core:
```shell
docker exec -it --user=solr solr bin/solr create_core -c test
```

Upload JSON data from [test_data.json](/test_data.json) file:
```shell
curl 'http://192.168.99.100:8983/solr/test/update?commit=true' --data-binary @test_data.json -H 'Content-type:application/json'
```
