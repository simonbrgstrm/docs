
---
title: "grep"
linkTitle: "grep"
date: 2017-01-05
description: >
  grep commands.
---

{{% pageinfo %}}
man grep
{{% /pageinfo %}}


GREP GREP

Search any line that contains the word bird in filename.
```shell
grep "bird" access.log
```

On multiple files.
```shell
grep "bird" access0.log access1.log access2.log
```

Case-insensitive search.
```shell
grep -i "bIrD" access.log
```

Search with regex.

```shell
grep -E "rs=[4-5,0]{3}" access.log
```

Count match and output sum.
```shell
grep -c "rs=500" access.log
```

Print num lines after match.
```shell
grep -A 10 "ERROR" app.log
```

Print num lines before match.
```shell
grep -B 10 "ERROR" app.log
```

Invert match.
```shell
grep -v "rs=200" access.log
```

Start slaming them pipes || 
```shell
grep "pub-k3y-1234-osv" access.log | grep "customerinvoice" | grep "rs=500"
```

