# Open telemetry with single traceid and span id

## Install jaeger

kubectl apply -f jaeger-deployment.yaml

port forward jaeger collector
kubectl port-forward svc/jaeger-collector  14268:14268

## run main

go run main.go

## Expose kuberentes proxy
kubectl proxy

## visit this UI to view Jaeger
http://localhost:8001/api/v1/namespaces/default/services/jaeger-query:80/proxy/search?end=1662231602802000&limit=20&lookback=1h&maxDuration&minDuration&service=trace-demo&start=1662228002802000