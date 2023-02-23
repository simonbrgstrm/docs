
---
title: "secrets"
linkTitle: "secrets"
date: 2023-02-23
description: >
  kubectl secret commands.
---

{{% pageinfo %}}
Secret documentation.
https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-em-secret-em-
{{% /pageinfo %}}


### Secrets

Create secret with no values
```shell
kubectl create secret generic NAME
```

Create file with passphrase value in it
```shell
echo -n "super secret" > ./passphrase
```

Create the secret using the passphrase file
```shell
kubectl create secret generic NAME --from-file=./passphrase
```

View the secret
```shell
kubectl describe secret NAME
```

View the contents of the secret
```shell
kubectl get secret NAME -o jsonpath='{.data}'
```

Decode the secret passphrase value
```shell
echo 'c3VwZXIgc2VjcmV0' | base64 --decode
```

Delete secret
```shell
kubectl delete secret NAME
```

