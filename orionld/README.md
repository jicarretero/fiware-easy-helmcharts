
# Helm deployment for ORION-LD

The `values.yaml` file consists of 3 different group of variables.

## MongoDB
Orion-ld uses MongoDB as its main database. So we'd need to deploy a local Mongo database for Orion-ld

reading the values file it should be quite self explanatory.

## OrionLD
Orion-ld set of variables to be deployed.


## Ingress
Should be set to false in Openshift.


# Use

```
helm install orionld $PWD
```

We could expose the service:
```
oc expose svc orionld-service
```

And to query the public endpoint, we could check the routes:
```
oc get route
```

Finally, to text that orionld broker is running, we could query:

```
$ curl http://whatever-the-route-it-was-defined/ngsi-ld/ex/v1/version
{
  "Orion-LD version": "post-v1.5.1",
  "based on orion": "1.15.0-next",
  "kbase version": "0.8",
  "kalloc version": "0.8",
  "khash version": "0.8",
  "kjson version": "0.8.2",
  "microhttpd version": "0.9.75-0",
  "rapidjson version": "1.0.2",
  "libcurl version": "7.68.0",
  "libuuid version": "UNKNOWN",
  "mongocpp version": "1.1.3",
  "mongoc version": "1.22.0",
  "bson version": "1.22.0",
  "mongodb server version": "5.0.26",
  "boost version": "1_67",
  "openssl version": "OpenSSL 1.1.1f  31 Mar 2020",
  "branch": "develop",
  "cached subscriptions": 0,
  "Core Context": "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context-v1.6.jsonld",
  "Next File Descriptor": 24
}
```

