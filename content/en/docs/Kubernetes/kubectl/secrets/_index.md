
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
```console
kubectl create secret generic NAME
```

Create file with passphrase value in it
```console
echo -n "super secret" > ./passphrase
```

Create the secret using the passphrase file
```console
kubectl create secret generic NAME --from-file=./passphrase
```

View the secret
```console
kubectl describe secret NAME
```

View the contents of the secret
```console
kubectl get secret NAME -o jsonpath='{.data}'
```

Decode the secret passphrase value
```console
echo 'c3VwZXIgc2VjcmV0' | base64 --decode
```

Delete secret
```console
kubectl delete secret NAME
```

