# redis-server

Deployment manifests for a Redis instance running on the cluster, using the
official [`redis`](https://hub.docker.com/_/redis) image with append-only
persistence backed by a `ceph-rbd-sc` PVC.

Exposed via a `LoadBalancer` Service in the `redis-server` namespace. No
`loadBalancerIP` is pinned; the address is assigned automatically by the
cluster's load balancer implementation and is stable across restarts and
Argo CD syncs.

Register with Argo CD: `kubectl apply -f argocd/application.yaml`
