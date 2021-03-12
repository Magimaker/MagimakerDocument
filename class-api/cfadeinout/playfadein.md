---
description: public void PlayFadeIn();
---

# PlayFadeIn

## 설명 

## 포탈을 통해 다음 방으로 넘어갈 때 사용하면 되는 함수. CFadeInOut.instance.PlayFadeFlow\(\)를 호출하여 화면전환을 진행하고 RefreshWorld\(\)를 호출하여 새로운 방을 생성하고 플레이어 캐릭터를 이동시킨다. 

```text
CPortalManager portalManager = GameObject.Find("PortalManager").GetComponent<CPortalManager>();
portalManager.MoveToNextRoom();
```

