
---
title: "misc"
linkTitle: "misc"
date: 2022-12-15
description: >
  misc commands.
---

{{% pageinfo %}}
Miscellaneous commands
{{% /pageinfo %}}


Move 10 random files from current dir to new dir
```shell
ls | shuf -n 10 | xargs -i mv {} path-to-new-dir
```

