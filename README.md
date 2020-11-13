# Simple HTTP Server

Demo application to test network

```shell
$ kubectl apply -f manifests/demo
```

```shell
$ kubectl -n service-a port-forward svc/service-a 8080:80
$ curl http://127.0.0.1:8080/?call=http://service-b.service-b
------------------------
From server: service-b-77999dfccb-kcqbx in cluster sandbox11
URL: /
Accept-Encoding: [gzip]
X-Forwarded-Proto: [http]
X-Request-Id: [f71b32d0-0fbb-4424-8d42-f6bacdef090f]
Content-Length: [0]
X-Forwarded-Client-Cert: [By=spiffe://cluster.local/ns/service-b/sa/default;Hash=c93c8891ba01fcbc2583205d8d123618bfffa627e18ddf76d5f2fe8d648fada5;Subject="";URI=spiffe://cluster.local/ns/service-a/sa/default]
X-Datadog-Trace-Id: [7084776759230572117]
X-Datadog-Sampling-Priority: [-1]
User-Agent: [Go-http-client/1.1]
X-Envoy-Attempt-Count: [1]
X-Datadog-Parent-Id: [440013331286411717]
------------------------
From server: service-a-6b5fd74c8-jcrdl in cluster sandbox11
URL: /?call=http://service-b.service-b
User-Agent: [curl/7.64.1]
Accept: [*/*]
```
