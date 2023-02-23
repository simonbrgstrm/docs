
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
kubectl create secret generic {NAME}
```

Create file with passphrase value in it
```shell
echo -n "super secret" > ./passphrase
```

Create the secret using the passphrase file
```shell
kubectl create secret generic {NAME} --from-file=./passphrase
```

View the secret
```shell
kubectl describe secret {NAME}
```

View the contents of the secret
```shell
kubectl get secret {NAME} -o jsonpath='{.data}'
```

Decode the secret passphrase value
```shell
echo 'c3VwZXIgc2VjcmV0' | base64 --decode
```

Create secret with values
```shell
kubectl create secret generic {NAME} --username=user --password=supersecret
```

Create secret from stdin
```shell
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  password: $(echo -n "supersecret" | base64 -w0)
  username: $(echo -n "user" | base64 -w0)
EOF
```

Edit secret
```shell
kubectl edit secret {NAME}
```

Delete secret
```shell
kubectl delete secret {NAME}
```

