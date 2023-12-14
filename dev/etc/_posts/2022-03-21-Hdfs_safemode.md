---
layout: post
title:  "HDFS Safemode"
date:  2023-03-21 00:16:26 +0900
categories: etc hdfs

---

> HDFS 의 세이프모드(safemode) 는 데이터 노드를 수정할 수 없는 상태
>
> - 데이터는 읽기 전용 상태가 되고, 데이터의 추가와 수정이 불가능
> - 데이터 복제도 불가능

# safemode command

- Safemode 상태 확인

```bash
hdfs dfsadmin -safemode get
```

- Safemode off (해제)

```bash
hdfs dfsadmin -safemode leave
```

- Safemode on (진입)

```bash
hdfs dfsadmin -safemode enter
```

