```bash
k create ns kubernetes-event-exporter
k -n kubernetes-event-exporter apply -f 01_serviceaccount.yaml
k -n kubernetes-event-exporter create secret generic event-exporter-cfg --from-file=config.yaml
k -n kubernetes-event-exporter apply -f 02_deployment.yaml
```