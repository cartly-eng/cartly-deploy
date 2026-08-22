# cartly-deploy

Kubernetes manifests for Cartly. ArgoCD (`argocd/shop.yaml`) syncs `apps/shop` to cluster
`aks-westus3-01`, namespace `shop`, automatically on every commit to `main`.

## Releasing a service

Bump the image tag (and `app.kubernetes.io/version`) in `apps/shop/<service>.yaml` to a tag built by
[cartly-shop](https://github.com/prateekkanurkar-cmd/cartly-shop) CI, commit, push. Roll back by
reverting the commit.

Secrets (`db-credentials`, `db-credentials-admin`) are provisioned out of band.
