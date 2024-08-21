## Redis Server in Kubernetes

### Steps to Deploy

1. Created a Redis pod using `pod.yml`.
2. Exposed the Redis pod using a NodePort service with `kubectl expose pod redis --type=NodePort --name=redis-svc`.
3. Accessed Redis using `redis-cli -h <Node-IP> -p <NodePort>`.

### Issues and Resolutions

- Issue: redis-kubernetes>redis-cli -h 192.168.65.3 -p 32063
'redis-cli' is not recognized as an internal or external command,
operable program or batch file.

- Resolution: kubectl run -it --rm --image=redis redis-cli -- redis-cli -h 192.168.65.3 -p 32063
