---
description: public void NotifyPortal();
---

# NotifyPortal

## 설명 

옵저버 패턴의 송신자 역할을 해주는 함수로써 이벤트가 끝났거나 몹이 다 죽었거나 등 포탈의 위치가 변경되어야 할 때 호출하는 함수다. 호출하게 되면 현재 리스트에 등록되어있는 모든 포탈의 OpenNClosePortal\(\)를 호출한다. 

```text
private void OnTriggerEnter(Collider coll)
{
    CCreateMap.instance.NotifyPortal();
}
```



