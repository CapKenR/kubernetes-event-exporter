Uses the Bitnami image of https://github.com/opsgenie/kubernetes-event-exporter.

For Elasticsearch, add an index using Management &rarr; Index Pattern &rarr; New Index Pattern &rarr; `kube-events-*`.

```bash
k create ns kubernetes-event-exporter
k -n kubernetes-event-exporter apply -f 01_serviceaccount.yaml
k -n kubernetes-event-exporter create secret generic event-exporter-cfg --from-file=config.yaml
k -n kubernetes-event-exporter apply -f 02_deployment.yaml
```