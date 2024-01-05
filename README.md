# cubix-cloudnative-block3-optional

Miskovits Dániel

# installation / deployment command (1 command)

```
kubectl apply -f .\application.yaml -n optional3
```

# 4 responses of the Header endpoint

1 Ingress
```json
{"Accept":["*/*"],"Accept-Encoding":["gzip, deflate, br"],"Host":["localhost:8080"],"Postman-Token":["6f960cb6-11e8-4cc5-b07b-13b5335b5b52"],"User-Agent":["PostmanRuntime/7.36.0"],"X-Forwarded-For":["172.18.0.1"],"X-Forwarded-Host":["localhost:8080"],"X-Forwarded-Port":["80"],"X-Forwarded-Proto":["http"],"X-Forwarded-Scheme":["http"],"X-Real-IP":["172.18.0.1"],"X-Request-ID":["61929984917a3ac13b9d238ac4e7066b"],"X-Scheme":["http"],"custom-header":["postman"]}
```

2 Kubernetes Service
```json
{"Accept":["*/*"],"Accept-Encoding":["gzip, deflate, br"],"Connection":["keep-alive"],"Host":["localhost:9080"],"Postman-Token":["4b04b93f-db89-42aa-992f-ac645780b85b"],"User-Agent":["PostmanRuntime/7.36.0"],"custom-header":["postman"]}
```

3 Pod directly
```json
{"Accept":["*/*"],"Accept-Encoding":["gzip, deflate, br"],"Connection":["keep-alive"],"Host":["localhost:9081"],"Postman-Token":["97452bf8-5e1f-4c94-9ed1-e0744096b487"],"User-Agent":["PostmanRuntime/7.36.0"],"custom-header":["postman"]}
```

4 Inside the Pod
```json
{"Accept":["*/*"],"Host":["localhost:8080"],"User-Agent":["curl/7.61.1"],"custom-header":["curl"]}
```

# command(s) for calling the Header endpoint inside the Pod

```
kubectl exec deploy/application -n optional3 -- sh -c "curl http://localhost:8080/header -H 'custom-header: curl' -s"
```

# command for copying the necessary file to the Pod

```
kubectl cp optional.txt application-575bc4c65-b8cqs:/deployments/optional.txt -n optional3
```

# response of the Data endpoint

MiskovitsDaniel-verymuchsecret-5137191644071

# delete namespace (and all resources in it)

```
kubectl delete namespace optional3
```
